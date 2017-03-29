# InetSysDev-GH-Community-Health
GHCommunityHealth is an enhancement project for [GHData](https://github.com/OSSHealth/ghdata) that
involves implementing new metrics and metric aggregation.  Like GHData, this is a Python project. 
For more information, see our
[System Description file](SystemDescription.md).

This repository is a staging ground for
code that could be added to GHData's codebase.  Code that is being submitted to GHData will be merged
into our [fork](https://github.com/kalepeterson/ghdata) before being included in a pull request to
OSSHealth's GHData.

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


# Contributions
We are currently not accepting contributions.  This file will be updated if that changes in the future.

# Licensing Information
This project is licensed under the MIT License.
See the [LICENSE](LICENSE) file.
All documentation is copyrighted under the Creative Commons Attribution 4.0 International Public License.
See the [DOCUMENT_LICENSE](DOCUMENT_LICENSE) file.

# Example Use Cases
* use cases, code snippets
