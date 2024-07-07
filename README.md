# Project Name: Fullstack Project with Shared Configuration

## Overview

This project demonstrates how to integrate multiple repositories (`frontend-repo` and `backend-repo`) into a unified project (`fullstack-repo`) using Git submodules. 
Each submodule has its separate repository on GitHub.

The project includes a shared configuration file (`config.yaml`) that is used by both submodules to adjust their behavior based on configuration settings.

## Project Structure

- **`fullstack-repo/`**: Unified project repository containing both frontend and backend as submodules.
  - **`config.yaml`**: Shared configuration file with settings which is `ServerIPAddress`.
  - **`frontend/`**: Submodule for frontend code (`frontend-repo`).
    - **`client.py`**: Python script for frontend operations.
  - **`backend/`**: Submodule for backend code (`backend-repo`).
    - **`server.py`**: Python script for backend operations.

## Setup Instructions

### Cloning the Repository

To clone the entire project including submodules, use the following command:

```bash
git clone --recursive https://github.com/Alirh1/fullstack-repo.git
```
If you have already cloned the repository without submodules, initialize and update them separately:

```bash 
git submodule update --init --recursive
```
Installing Dependencies
Ensure you have Python installed. This project uses Python 3 and requires the pyyaml library 

for parsing YAML files. Install pyyaml using pip:
```bash
pip install pyyaml
```
## Running the Project
**`Backend (backend-repo)`**:
 - Navigate to the backend-repo directory:
 ```bash
 cd backend-repo
 ```
 - Run the server.py script:
 ```bash
 python server.py
 ```

This script reads config.yaml from the root of fullstack-repo and checks the run_localhost setting. If ```ServerIPAddress``` is not ```127.0.0.1```, it prints an error message indicating the server cannot run on localhost.

**`Frontend (frontend-repo)`**:
 - Navigate to the frontend-repo directory:
 ```bash 
 cd frontend-repo
 ```
 - Run the client.py script:
 ```bash
 python client.py
 ```

Similar to the backend, this script also reads config.yaml and checks the run_localhost setting. If run_localhost is true, it prints an error message indicating the client cannot run on localhost.

## How It Works
- Submodules: Submodules (frontend and backend) are included in fullstack-repo and maintain their separate repositories on GitHub.
- Shared Configuration: Both server.py and client.py scripts in backend-repo and frontend-repo respectively, load configuration settings from config.yaml.
- Error Handling: If ```ServerIPAddress``` is not ```127.0.0.1``` in config.yaml, both scripts respond appropriately by printing an error message indicating localhost restrictions.

