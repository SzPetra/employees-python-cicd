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
docker compose up -d: will run it in the background so won't see logs in terminal, that's because of the "-d" flag, if logs are needed, leave flag
--abort-on-container-exit flag: when tests are done, it will exit containers and stops them
docker compose --profile ui-test up (--abort-on-container): docker compose --profile "profile name" up, so I don't have to make multiple docker files only one and run only the profiles I would like to
docker build -t employees-python-test f Dockerfile.test .

pip install.[dev]: when wanting to install different dependencies than default (based on project.toml line 18)

set EMPLOYEES_URL=http://localhost:81 -> to set another environment variable from command line

When getting CACHED while building docker checks if file has been changed and if not it takes it from cache instead of building all over again:
 => CACHED [2/5] WORKDIR /app                                                                                      0.0s
 => CACHED [3/5] COPY *.toml *.txt .                                                                               0.0s
 => CACHED [4/5] RUN pip install -c constraints.txt .                                                              0.0s
 => CACHED [5/5] COPY *.py . 

ENTRYPOINT ["gunicorn", "--bind", "0.0.0.0:5000", "employees:app"]
--bind means that when the app runs it will also run on host computer localhost:5000 not just in container localhost:5000

### HOW TO RUN TESTS ###
pytest test/unit -v: pytest "directory of test(no need to include the exact file only if there are more than one)" verbose, more detailed result of test

pre-commit run --all-files: to use the pre-commit on every single files 
