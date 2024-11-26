python -m venv ven: creates venv directory -> scripts directory with the name "ven"

pip install --editable . -> download dependencies and libraries for project
pip freeze --exclude-editable > constraints.txt
-> from now on to install -> python -m install -c constraints.txt

flask --app employees run --debug

venv/scripts/activate.ps1

run -p 80:80 -d nginx: port forward to the container's 80 port (first one is my machine) (-d: detach)
docker ps: processes
docker ps -a: 
docker stop ID/pin: stop image
docker start ID/pin: start image
docker rm ID/pin: delete 
docker exec -it employees-postgres ls -l
docker exec -it employees-postgres bash: logged into docker -> exit to step out
docker build -t hello-world-python .: building the container, -t cause it takes the image name as a tag
docker images: listing all images 
docker run "image name": run image/docker (hello-world-python)

When getting CACHED while building docker checks if file has been changed and if not it takes it from cache instead of building all over again:
 => CACHED [2/5] WORKDIR /app                                                                                      0.0s
 => CACHED [3/5] COPY *.toml *.txt .                                                                               0.0s
 => CACHED [4/5] RUN pip install -c constraints.txt .                                                              0.0s
 => CACHED [5/5] COPY *.py . 

ENTRYPOINT ["gunicorn", "--bind", "0.0.0.0:5000", "employees:app"]
--bind means that when the app runs it will also run on host computer localhost:5000 not just in container localhost:5000