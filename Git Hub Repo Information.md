To achieve this task, you can use the GitHub API to fetch details of repositories and then use a programming language like Python to store the information in a CSV file. Here's an example code using Python and the requests library:

```python
Copy code
import requests
import csv

def fetch_github_repositories(username, token):
    url = f'https://api.github.com/users/{username}/repos'
    headers = {'Authorization': f'token {token}'}
    
    response = requests.get(url, headers=headers)
    
    if response.status_code == 200:
        return response.json()
    else:
        print(f"Failed to fetch repositories. Status code: {response.status_code}")
        return None

def store_repositories_in_csv(repositories, csv_file):
    with open(csv_file, 'w', newline='') as file:
        writer = csv.writer(file)
        # Write header row
        writer.writerow(['Repository Name', 'Description', 'URL'])
        
        # Write data rows
        for repo in repositories:
            writer.writerow([repo['name'], repo['description'], repo['html_url']])

if __name__ == "__main__":
    # Replace 'YOUR_GITHUB_USERNAME' and 'YOUR_PERSONAL_ACCESS_TOKEN' with your GitHub username and personal access token.
    github_username = 'YOUR_GITHUB_USERNAME'
    github_token = 'YOUR_PERSONAL_ACCESS_TOKEN'
    
    repositories = fetch_github_repositories(github_username, github_token)
    
    if repositories:
        csv_file = 'github_repositories.csv'
        store_repositories_in_csv(repositories, csv_file)
        print(f"GitHub repositories details have been stored in {csv_file}")
```
Make sure to replace 'YOUR_GITHUB_USERNAME' and 'YOUR_PERSONAL_ACCESS_TOKEN' with your GitHub username and personal access token. Also, note that using a personal access token is recommended for authentication when making requests to the GitHub API.

This script fetches the repositories of a specified GitHub user, extracts relevant information (repository name, description, and URL), and stores it in a CSV file named github_repositories.csv.