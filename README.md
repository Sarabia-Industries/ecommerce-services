## Development

1. Clone the repository
2. Create a `.env` file based on the `.example.env`
3. Run the command `git submodule update --init --recursive` to rebuild the submodules
4. Run the command `docker compose up --build`

### Steps to Create Git Submodules

1. Create a new repository on GitHub
2. Clone the repository on your local machine
3. Add the submodule, where `repository_url` is the URL of the repository and `directory_name` is the name of the folder where you want the submodule to be stored (the directory must not exist in the project)

    ```sh
    git submodule add <repository_url> <directory_name>
    ```

4. Add the changes to the repository (git add, git commit, git push)

    ```sh
    git add .
    git commit -m "Add submodule"
    git push
    ```

5. Initialize and update submodules: when someone clones the repository for the first time, they should run the following command to initialize and update the submodules

    ```sh
    git submodule update --init --recursive
    ```

6. To update submodule references

    ```sh
    git submodule update --remote
    ```

## Important

If you are working in a repository with submodules, **first update and push** in the submodule and **then** in the main repository. If done in reverse, submodule references in the main repository will be lost, causing conflicts that need to be resolved.

# Production

1. Clone the repository
2. Create a `.env` file based on the `.env.template`
3. Run the command

    ```sh
    docker compose -f docker-compose.prod.yml build
    ```
