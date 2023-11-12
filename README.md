

# CasaOs Konmeo JupyterLab Docker Compose
Runing JupyterLab Notebook on CasaOS Server with aarch64
Based on [Konmeo/jupyterLab](https://hub.docker.com/r/konmeo/jupyterlab)
- How to use:
1. On Casaos Home.
2. click on "+".
3. Click on add custom image.
4. Click on import icon.
5. select the [JupyterLab.yaml](https://github.com/hqnicolas/CasaOsJupyterLab/blob/main/jupyterlab.yaml)
- to change your docker external port, edit the [JupyterLab.yaml](https://github.com/hqnicolas/CasaOsJupyterLab/blob/main/jupyterlab.yaml):
```
published: "3000"
```
- Now you can aceess: http://casaos.yourserver:3000
- How to access the login token:
1. On Casaos Home
2. Click on JupyterLab Config
3. Click on Terminal and Logs
4. on Logs, Find this line:
```
Running at:
jupyterlab-jupyterlab-1  | [I 2023-11-12 10:42:05.636 ServerApp] http://localhost:8888/lab?token=c5ad99bf763ebc0
```
5. Take the token from Link above.
6. Drop the token on your JupyterLab Login Screen.
- [This file](https://github.com/hqnicolas/CasaOsJupyterLab/blob/main/jupyterlab.yaml) is Based on Comand:
```
docker run -i -t -p 3000:8888 -v "$PWD":/workspace --name jupyterlab konmeo/jupyterlab /bin/bash -c "\
jupyter lab \
--notebook-dir=/workspace --ip='*' --port=8888 \
--no-browser --allow-root"
``` 
- Your Jupiter will access your USER folder From CasaOS Linux server.
