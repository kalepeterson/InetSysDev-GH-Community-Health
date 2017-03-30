# System Description
Our project is to enhance the amount and variety of data available to the newly developed and growing GHData user interface.
In order to accomplish this, new functions will be added to the GHData class found in ghdata.py that will retrieve new data sets from GHTorrent.
Originally we planned on developing a seperate module that extended the functionality of ghdata by creating aggregate metrics. After beginning development we pivoted away from this idea and instead decided on implementing the aggregate metrics directly within the existing ghdata project files. We decided to do this because we realized that the aggregate metrics are best generated from directly querying the ghdata database. 


In addition to extending the functionality of GHData, the project will also include a research portion involving possible methods of identifying maintainers of a repository using GHTorrent data.
Although such a method may not be completely accurate, an estimate would still be valuable information for users of GHData.
If a solution is identified, then it will also be integrated into the GHData class as part of the other enhancements.
It would then be possible to send the maintainer data to the new timeline module, which would show the change in maintainers over time.

# Implemented Metrics

# Proposed Metrics
Here is a list of metrics that we are considering adding to GHData:
* Pull Requests
    * Time to Close (closed_at - created_at)
        * Average for repository
    * Percentage merged
* Issues
    * Amount created between releases
        * Immediately after release (bugs)
    * Comments
        * Timeliness
        * Average amount per issue
* Release rate
* Aggregate Metrics
    * Issues to Pull Requests ratio
        * Issues / Pull Requests
            * High: lots of discussion, not much merging
    * Open Issues to Contributors/Active Contributors
* Identifying maintainers
            

# Data Flow Diagram
![Data Flow Diagram](Data%20Flow%20Diagram%20Revised.png "Data Flow Diagram")
