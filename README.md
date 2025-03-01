# Simple file listing

## Original
Initial version of the script
- try's to mount a shared google drive

## 2025-02-28 Version
Follow up version that includes extra tools to start, restart docker container, and restart Docker Desktop to establish how to gain a connection with a Goolge Shared Drive

### Start docker container ```1startDocker.bat```
This will start the docker container

### Re-Start docker container ```1reStartDocker.bat```
This will re-start the docker container

### Login into the container ```2loginDockerContainer.bat```
This allows to log into the docker container and then navigate to a Google sharedFolder or ownedFolder and see if files are listing
```shell
cd shareDrive
ls 
```
- If files appear it means the connection with the Google Shared drive is working

```shell
cd ownedDrive
ls
```
If files appear it means the connection with a Google drive that is owned by the user is working

### Re-Establish Google Drive Connection
Initial script to address the connection issues to a Google Shared Drive
```shell
./reEstablishGoogleDriveConnection.bat
```
This will shutdown the wsl engine and cause Docker Desktop to restart

### Config
You must add your own paths to the sharedFolder and ownedFolder in your docker-compose file that adhere to your local computer configuration
- Ensure Google drive is set to Mirror not Stream

```shell
    volumes:
      - /g/Shared drives/change-to-your-google-shared-drive-path:/app/shareDrive
      - /C/Users/sacha/My Drive-change-to-your-local-owned-google-drive-path:/app/ownedDrive
```