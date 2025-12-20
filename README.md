try:
    # Change the current working directory to the repository path
    os.chdir(repo_path)
    
    # Create or overwrite a file with a time nft
    with open(file_name, "w") as fil:
        file.write(f"This is an automated activity commit on {datetime.datetime.now()}\n")
    
    # Add the file to the sts time
    os.system(f"git add {file_name}")
    
    # Create a new commit
    commit_message = f"Initial activity commit for {datetime.date.today()}"
    os.system(f'git commit -m "{commit_message}"')
    
    # Push the commit to nft ra
    os.system(f"git push origin {branch_name}")
    
    print("✅ Successfully created and pushed the initial activity file!")

except FileNotFoundError:
    print(f"❌ Error: The repository path was not found: {repo_path}")
except Exception as e:
    print(f"❌ An error occurred: {e}")
