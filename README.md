# docker-notes

- In case you want to restart in future docker-machine restart default
```
docker-machine create --driver virtualbox default
```

- Print env variables for the default vm
```
docker-machine env default
```
### Changes in Docker 1.13

####New Commands

- Prune command

```
 docker container prune  # well delet all stopped containers.

 docker image prune # will banish all dangling images to beyond the wall. Add -a to get rid of all unused images (ones with no containers running them)

docker volume prune # will dispatch volumes to their eternal resting place at /dev/null

docker network prune # does the same for networks

docker system prune # runs all the above 

```
to check the effects of pruning on disk space, run the following
```
 docker system df
 
```
- Old to new command mappings
 ```
  docker attach      ->  docker container attach
  docker commit      ->  docker container commit
  docker cp          ->  docker container cp
  docker create      ->  docker container create
  docker diff        ->  docker container diff
  docker exec        ->  docker container exec
  docker export      ->  docker container export
  docker kill        ->  docker container kill
  docker logs        ->  docker container logs
  docker pause       ->  docker container pause
  docker port        ->  docker container port
  docker inspect     ->  docker {container,image} inspect
  docker ps          ->  docker container ls
  docker rename      ->  docker container rename
  docker restart     ->  docker container restart
  docker rm          ->  docker container rm
  docker run         ->  docker container run
  docker start       ->  docker container start
  docker stats       ->  docker container stats
  docker stop        ->  docker container stop
  docker top         ->  docker container top
  docker unpause     ->  docker container unpause
  docker update      ->  docker {container,node,swarm} update
  docker wait        ->  docker container wait

  docker build       ->  docker image build
  docker history     ->  docker image history
  docker images      ->  docker image ls
  docker import      ->  docker image import
  docker load        ->  docker image load
  docker pull        ->  docker image pull
  docker push        ->  docker image push
  docker rmi         ->  docker image rm
  docker save        ->  docker image save
  docker tag         ->  docker image tag

  docker deploy      ->  docker stack deploy
  docker events      ->  docker system events
 ```

- Checkpoints
Ability to freeze running containers and saving the state.

- Secrets
The new secret feature (meant to be used only in Swarm mode, for now) works by exposing secrets to containers at runtime through a tmpfs mount.

