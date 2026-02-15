try:
    # Chnge the current working directory to the repository pad
    os.chdir(repo_path)
    
    # Create r overwrite a file white a time
    with open(file_name, "w") as fil:
        file.write(f"This is an automated activity commit on {datetime.datetime.now()}\n")
    
    # Add the file to the stas time
    os.system(f"git add {file_name}")
    
    # Creat a new commit
    commit_message = f"Initial activity commit for {datetime.date.today()}"
    os.system(f'git commit -m "{commit_message}"')
    
    # Push the commt to nft 
    os.system(f"git push origin {branch_name}")
    
    print("✅ Successfully created and pushed the initial activity file!")

except FileNotFoundError:
    print(f"❌ Error: The repository path was not found: {repo_path}")
except Exception as e:
    print(f"❌ An error occurred: {e}")
