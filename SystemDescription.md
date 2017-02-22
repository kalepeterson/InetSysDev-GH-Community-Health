# System Description
Our project is to enhance the amount and variety of data available to the newly developed and growing GHData user interface.
In order to accomplish this, new functions will be added to the GHData class found in ghdata.py that will retrieve new data sets from GHTorrent.
Additionally, a new module will be developed that will extend the use of the “__predicate_dates” function by creating timeline objects that show the slope of a repository’s metrics.
For example, one such use of the new module would be to obtain an object that contained the amount of forks on a repository at certain points in time, as well as what relative change exists between those amounts.
This could be useful information for displaying how a repository has adapted over time.

In addition to extending the functionality of GHData, the project will also include a research portion involving possible methods of identifying maintainers of a repository using GHTorrent data.
Although such a method will probably not be completely accurate, an estimate would still be valuable information for users of GHData.
If a solution is identified, then it will also be integrated into the GHData class as part of the other enhancements.
It would then be possible to send the maintainer data to the new timeline module, which would show the change in maintainers over time.

![Data Flow Diagram](Data%20Flow%20Diagram.jpg "Data Flow Diagram")