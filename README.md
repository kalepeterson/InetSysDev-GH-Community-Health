# InetSysDev-GH-Community-Health
GHCommunityHealth is an enhancement project for [GHData](https://github.com/OSSHealth/ghdata) that
involves implementing new metrics and metric aggregation.  Like GHData, this is a Python project. 
For more information, see our
[System Description file](SystemDescription.md).

This repository is a staging ground for
code that could be added to GHData's codebase.  Code that is being submitted to GHData will be merged
into our [fork](https://github.com/kalepeterson/ghdata) before being included in a pull request to
OSSHealth's GHData.

# Dependencies
* [Python](https://www.python.org/downloads/) 3.4.x
* [MySQL](https://dev.mysql.com/downloads/) 5.x or later version (can be on a separate machine)
* [GHTorrent](http://ghtorrent.org/) in database
* [Pip](https://pip.pypa.io/en/stable/installing/)

# Installation
1. Download and import the GHTorrent MSR14 database. The link to download the dataset and installation instructions can be found [here](http://ghtorrent.org/msr14.html). The database import process can be done using MySQL workbench as well, which is mentioned [here](https://github.com/OSSHealth/ghdata#step-3-optional-if-you-are-able-to-get-the-full-database---install-a-small-local-testing-database)
2. Execute the command `pip install --upgrade https://github.com/kalepeterson/ghdata/archive/milestone3-v1.zip` from a command prompt or terminal to download and install our version of ghdata. If you are on a Mac or Linux machine you may need to execute `sudo pip install --upgrade https://github.com/kalepeterson/ghdata/archive/alpha-v6.zip` to install ghdata.
3. Execute the command `ghdata` from your command prompt or terminal to generate the ghdata.cfg configuration file.
4. Open ghdata.cfg in your text editor of choice and edit the configuration to match your local database settings.
5. Execute the command `ghdata` once again to start the server.
6. Open browser and navigate to the server's API endpoints. (See the "Testing the New REST Endpoints" section below)

* Installation has been tested on Windows 10 PC's and has not been verified to work on Mac or Linux yet.

# Development Environment
This project will be developed in Python using the JetBrains PyCharm IDE.

## Versions Used
PyCharm 2017.1 
Build #PY-171.3780.115, built on March 24, 2017 
JRE: 1.8.0_112-release-736-b13 x86 
JVM: OpenJDK Server VM by JetBrains s.r.o 
Windows 10 10.0

PyCharm 2016.3 
Build #PY-171.3651.112, built on December 28, 2016 
JRE: 1.8.0_112-release-736-b13 x86 
JVM: OpenJDK Server VM by JetBrains s.r.o 
Windows 10 10.0

# Testing GHCommunityHealth
## Running Tests using PyCharm IDE

To run tests for the project in PyCharm you will need to Edit the Configuration for the test_ghdata.py file.

1. Click on the Run file dropdown in the top right of PyCharm and select 'Edit Configuration'

![Edit Configuration Location](https://raw.githubusercontent.com/kalepeterson/ghdata/dev/test/Resources/Doc_PyCharmTest_1.png "Edit Configuration")
2. Click on the Add button in the top left to add a new configuration. Select "Python test" \> "py.test"
![Py.Test Setup](https://raw.githubusercontent.com/kalepeterson/ghdata/dev/test/Resources/Doc_PyCharmTest_2.png "Test Setup")
3. Select the Target Path to the location of the test file on your system.
4. Add Your database connection to the Environmental Variables field in the form: `DB_TEST_URL=DB_TEST_URL=mysql+pymysql://{user}:{password}@{host}:{port}/{name}`
![Py.Test Configuration](https://raw.githubusercontent.com/kalepeterson/ghdata/dev/test/Resources/Doc_PyCharmTest_3.png "Test Configuration")

5. Click Ok to save your configuration.

6. Select and run the new configuration.

## Testing the new REST endpoints

Several new endpoints have been added.
For testing, simply visit the list of URLs below to view the generated JSON output.
These test URLs target the "shiny" repository by user "rstudio" since it returns data for every new endpoint.
The target repository can be changed to any user/repository combination that is included in the MSR14 data set by simply 
replacing "shiny" with the new repository name and "rstudio" with the new user login name.
These can be accessed after successfully starting an instance of our forked ghdata project.

* Forks
    * All: [http://127.0.0.1:5000/unstable/rstudio/shiny/forks](http://127.0.0.1:5000/unstable/rstudio/shiny/forks)
    * Year: [http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/forks/year](http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/forks/year)
    * Month: [http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/forks/month](http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/forks/month)
    * Week: [http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/forks/week](http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/forks/week)
    * Day: [http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/forks/day](http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/forks/day)
* Issue actions
    * All: [http://127.0.0.1:5000/unstable/rstudio/shiny/issue_actions](http://127.0.0.1:5000/unstable/rstudio/shiny/issue_actions)
* Stargazers (actually watchers)
    * Year: [http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/stargazers/year](http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/stargazers/year)
    * Month: [http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/stargazers/month](http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/stargazers/month)
    * Week: [http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/stargazers/week](http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/stargazers/week)
    * Day: [http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/stargazers/day](http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/stargazers/day)
* Pull Requests
    * Year: [http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/pulls/year](http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/pulls/year)
    * Month: [http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/pulls/month](http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/pulls/month)
    * Week: [http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/pulls/week](http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/pulls/week)
    * Day: [http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/pulls/day](http://127.0.0.1:5000/unstable/rstudio/shiny/timeseries/pulls/day)
* Average Issue Response Time
    * [http://127.0.0.1:5000/unstable/rstudio/shiny/issues/average_response](http://127.0.0.1:5000/unstable/rstudio/shiny/issues/average_response)
* Relative Activity
    * Ratio: [http://127.0.0.1:5000/unstable/rstudio/shiny/relative_activity](http://127.0.0.1:5000/unstable/rstudio/shiny/relative_activity)
    * Project Members: [http://127.0.0.1:5000/unstable/rstudio/shiny/relative_activity_pm](http://127.0.0.1:5000/unstable/rstudio/shiny/relative_activity_pm)
    * Non Project Members: [http://127.0.0.1:5000/unstable/rstudio/shiny/relative_activity_nonpm](http://127.0.0.1:5000/unstable/rstudio/shiny/relative_activity_nonpm)

# Database Schema
This project will not be using a schema that is distinct from GHData.
We will be utilizing the infrastructure that GHData currently has in place.
GHData uses the GHTorrent database, the schema of which can be found [here](http://ghtorrent.org/files/schema.png).

# Primary Use Case
Since this project primarily affects the REST API of ghdata, the primary use case is for other applications consuming the
information that our enhancements provide.

**Title**: Consume Health and Sustainability Metrics for an Open Source Repository

**Primary Actor**: Consuming software application, either external or the ghdata user interface.

**Goal in Context**: The consuming application is able to retrieve a variety of useful metric data for a specified repository.

**Stakeholders**:

    * Consuming application users: To receive useful and accurate metric information.
    * Consuming application developers: To receive metric information for processing.

**Preconditions**:
    
    * Instance of ghdata and current GHTorrent database are running on an accessible server.
    * Consuming application developers understand the ghdata API and have developed an application to use the endpoints.
    
**Main Success Scenario**: The consuming application's users are presented with the desired metric information.

**Failed End Conditions**: The consuming application fails to process the information from ghdata or the information
is outdated or inaccurate.

**Trigger**: Consuming application makes requests to the ghdata REST API endpoints.


# Contributions
We are currently not accepting contributions.  This file will be updated if that changes in the future.

# Licensing Information
This project is licensed under the MIT License.
See the [LICENSE](LICENSE) file.
All documentation is copyrighted under the Creative Commons Attribution 4.0 International Public License.
See the [DOCUMENT_LICENSE](DOCUMENT_LICENSE) file.


