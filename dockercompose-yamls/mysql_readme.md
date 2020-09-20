# mysql docker copose yaml
run 

    docker-compose -f mysql.yaml pull 
    docker-compoes -f mysql.yaml up -d 

In this docker compose yaml, a user variable is set to the root user (with uid 0).  
You can change the user by updating {uid}:{groupid}. Before doing that, make sure the user you are going to define has the write access
to the volume folder in the host system (left part of the volume definition in the yaml).  If this is not set properly, you may experience
some permission error inside the mysql docker container.  

some references regarding permission error: 

* [ERROR chown: changing ownership of '/var/lib/mysql/': Operation not permitted](https://github.com/docker-library/mysql/issues/396#issuecomment-376650503)
* [ERROR permission denied while mounting volume](https://github.com/docker-library/percona/issues/75#issuecomment-442537828)
* [docker compose user guideline](https://docs.docker.com/engine/reference/run/#user)

