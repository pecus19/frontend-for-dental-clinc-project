# iti0302-frontend

## Local installation guide
### Clone the source code
- Clone the frontend repository (https://gitlab.cs.ttu.ee/agorbo/iti0302-frontend)
- Check out the 'main' branch
### Run the application
- Install Node.js
- Run 'npm install' to install all the required dependencies
- Run 'npm run dev' for the frontend application to run

## Remote installation guide
### Locate the frontend directory
- Connect to the server via SSH ('ssh -l ubuntu 193.40.255.20')
- Go to the frontend directory ('cd /opt/dentalclinic-frontend')
### Compose up the project
- Create docker compose file ('docker-compose.yml') with the contents of the 'docker-compose-server.yml' from the repo
- Run 'docker compose down', 'docker compose pull', 'docker compose up -d' to stop, update, and run containers with the frontend application
