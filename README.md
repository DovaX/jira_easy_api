# jira_easy_api
A wrapper around Jira API to run jira commands missing in their UI as oneliners


## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install jira_easy_api.

```bash
pip install jira_easy_api
```

## Usage

```python
from jira_easy_api_core import JiraClient

jira_api_token="2pU1YDiGagbISzfGgDzfzE5C"
jira_workspace_url='https://your_workspace.atlassian.net'


jc=JiraClient(jira_workspace_url,"your_email@gmail.com",jira_api_token) #Initialize Jira Client

issues=jc.get_all_issues_by_project_name("FP") #Get all issues/tasks
jc.create_new_issue("FP", "Test task", "It works!") #Create new issue/task
jc.update_issue_by_name("FP-377",{"description":"Test"}) #Update existing issue/task

issues=jc.get_all_issues_by_project_name("FP")
issue_ids=[str(issue) for issue in issues]
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
[MIT](https://choosealicense.com/licenses/mit/)

## Currently implemented

* Get all issues
* Create new issue
* Update issue
* Delete issue
