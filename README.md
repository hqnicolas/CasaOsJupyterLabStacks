

# CasaOs JupyterLab Docker Stacks Oficial image Compose
Runing JupyterLab Notebook on CasaOS Server with aarch64
Based on [jupyterLab Base Notebook](https://quay.io/repository/jupyter/base-notebook)
- How to use:
1. On Casaos Home.
2. click on "+".
3. Click on add custom image.
4. Click on import icon.
5. select the JupyterLab.yaml
- to change your docker external port, edit the [JupyterLab.yaml](https://github.com/hqnicolas/CasaOsJupyterLabStacks/blob/main/jupyterlab.yaml)
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
- [This file](https://github.com/hqnicolas/CasaOsJupyterLabStacks/blob/main/jupyterlab.yaml) is Based on Comand:
```
podman pull quay.io/jupyter/base-notebook
docker run -it --rm -p 3000:8888 -v "${PWD}":/home/jovyan/work quay.io/jupyter/base-notebook
``` 
- Your Jupiter will access your USER folder From CasaOS Linux server.
