# System Description
Our project is to enhance the amount and variety of data available to the newly developed and growing GHData user interface.
We are placing a focus on aggregate metrics, specifically ratios of different metrics or composites of multiple metrics
that provide more information than their components.
There is a list of the new metrics we are adding in the Metrics section below.

In order to accomplish this, new functions will be added to the GHData class found in ghdata.py that will retrieve new data sets from GHTorrent.
Originally we planned on developing a seperate module that extended the functionality of ghdata by creating aggregate metrics. 
After beginning development we pivoted away from this idea and instead decided on implementing the aggregate metrics 
directly within the existing ghdata project files. 
We decided to do this because we realized that the aggregate metrics are best generated from directly querying the ghdata database. 

However, we are still enhancing the existing time series functions of ghdata by extending the usefulness of the 
`__single_table_count_by_date` function by allowing the data to be grouped by year, month, week, and day.
This function previously only allowed data to be grouped by week.
For example, one such metric that uses the `__single_table_count_by_date` function is the number of times a repository 
was forked in a given time frame.
With our changes, this information is now also available in yearly, monthly, and daily forms, resulting in facilitating 
the creation of a Tableau-like user interface in the future.

In addition to extending the functionality of GHData, the project also includes a research portion involving possible 
methods of identifying maintainers of a repository using GHTorrent data.
Although such a method may not be completely accurate, an estimate would still be valuable information for users of GHData.
If a solution is identified, then it will also be integrated into the GHData class as part of the other enhancements.
It would then also be possible to see how much experience a repository's maintainers have on GitHub in a time series.

# Metric Retrieval and Representation
The GHData project is a Python Flask web application that queries a local GHTorrent MySQL database in order to retrieve 
and manipulate GitHub metadata into usable metrics in the form of JSON objects.
The resulting JSON objects are simply translated from the data table brought back from the queries.
The table's columns are the keys and the rows populate the values.
Here is an example of the JSON returned by GHData showing the number of forks created by year off of the doom3.gpl repository:

`[

    {

        "date" : "2011-11-22T00:00:00.000Z",
  
        "projects" : 266
  
    },
  
    {
  
        "date" : "2012-01-02T00:00:00.000Z",
  
        "projects" : 169
  
    },
  
    {
  
        "date" : "2013-01-03T00:00:00.000Z",
  
        "projects" : 178
  
    }

]`

Once an instance of our fork of ghdata is running, this data can be retrieved by visiting the following URL in a browser:
[http://127.0.0.1:5000/unstable/TTimo/doom3.gpl/timeseries/forks/year](http://127.0.0.1:5000/unstable/TTimo/doom3.gpl/timeseries/forks/year)

# Implemented Metrics
 * Stargazers (actually watchers) grouped by day, week, month, and year
    * Measures public interest in a project.
 * Pull Requests grouped by day, week, month, and year
    * Shows activity on a project over time.
 * Forks
   * All forks of a certain repository
        * Mainly useful for future user interface work (e.g. traversing between forks, getting metrics for forks as well)
   * Grouped by day, week, month, and year
        * Useful for measuring interest or new development on a project.
 * Issue Actions
    * Mostly useful for developing more complex metrics, but also provides a look at what actions are common, such as
    mentions, reopenings, and more.
 
# Proposed Metrics
Here is a list of metrics that we are considering adding to GHData:
* Activity on forks
    * Could be useful from a corporation point of view.  If a certain fork has a lot of activity, it could mean that
    the community is split on a certain issue or feature.
* Pull Requests
    * Average Time to Close (closed_at - created_at, aggregated)
        * Time to close is already implemented, but the average for a repository might be useful to know for path to 
        maintainership and/or barriers to entry for committers.  If the value is high, then maybe certain pull requests are allowed to be fixed and eventually merged.
* Issues
    * Amount created between releases
        * Issues created immediately after a release could be a sign of bugs, which is a very important consideration for
        most potential contributors and users.
    * Amount of each action taken on an issue
        * Mostly useful for developing more complex metrics, but also an easy way to see what typically happens to an issue over time.
* Release rate
    * Useful for organizations who might want to upstream the project.  If releases are slow, new features will also be realized slowly.
* Issues to Pull Requests ratio
    * Issues / Pull Requests
        * High values would indicate lots of discussion, but not much merging
    * Open Issues to Contributors / Active Contributors
* Identifying maintainers
    * Experience on GitHub, i.e. how old the account is (user's created_at column)            

# Data Flow Diagram
![Data Flow Diagram](Data%20Flow%20Diagram%20Revised.png "Data Flow Diagram")
