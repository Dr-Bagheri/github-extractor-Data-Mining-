Step 1: First, it is neccessary (or at least highly recommended) to get a github API access token. Create it here: https://github.com/settings/tokens. Save the token in a file called 'access' in the same folder as the python scripts. To download a lot of commits, the following script is used: By modifying it, the keywords that are used to fetch the commits can be altered. The results are saved in 'all_commits.json'.

```
python3 github.py
```
Step 2: Repositories that are just there to demonstrate a vulnerability, to set up a capture-the-flag-type of challenge, or carry out an attack are not desireable for the dataset. The repository name and the content of the readme.md file are checked with the following script to filter out some of those already. The results are saved in DataFilter.json, which keeps track of the 'flags' set for each repository.
```
python3 filter-data.py
```


Step 3: Next, the commits are checked to see if they contain python code, and to download the diff files. While this is done, the file 'DataFilter.json' is saved to store information about which repositories and commits contain python and which don't (in addition to the info about showcases). The resulting data with the commits itself is stored in the file PyCommitsWithDiffs.json.

```
python3 get-data.py
```

