# Jumping Jack
A project that demonstrates how to deploy directly from a single git repo to multiple images

## WARNING

This example is for learning purposes only and is not appropriate for production.  See [Jack](https://github.com/nicholaskajoh/jack) for details how to add security and deploy in production.

## Try it

Run
```shell
curl -L -o /tmp/docker-compose.yml https://raw.githubusercontent.com/andrewspringman/jumpingJack/master/docker-compose.yml && docker-compose -f /tmp/docker-compose.yml up
```
Then browse to
```
http://localhost
http://app.localhost
http://blog.loclhost
```

## Credits

### Nicholas Kajoh
I really enjoyed [Nicholas Kajoh's article on running multiple apps with Docker and Traefik](https://medium.com/@nicholaskajoh/how-to-run-multiple-apps-on-one-server-using-docker-and-traefik-de3f6a5ddb4c).  He provides [a github repo of the project](https://github.com/nicholaskajoh/jack).  It provides a great starting point for learning Docker and Traefik.  This is a fork of [that repo](https://github.com/nicholaskajoh/jack).

### Sebastiaan van Stijn
[Sebastiaan van Stijn (GitHub user @thaJeztah)](https://github.com/thaJeztah) gives [the syntax for specifying a specific branch and subdirectory of a git repo as the build context](https://github.com/moby/moby/issues/7071#issuecomment-234306681).  A little testing shows that this works with the build command in a docker-compose.yml file as well.

### Rain
[GitHub user @rainbreak](https://github.com/rainbreak) provides [a method for cloning a github repo directly into an image that prevents cloning if the branch hasn't changed](https://github.com/moby/moby/issues/14704#issuecomment-215961707).

### Josh Fox
[Josh Fox (Stack Exchange id CelticParser)](https://askubuntu.com/users/384425/celticparser) provides [a method for cloning a subtree of a repo](https://askubuntu.com/questions/460885/how-to-clone-git-repository-only-some-directories/729798#729798).

### Joffrey F
[Joffrey F (GitHub user shin-)](https://github.com/shin-) suggests [using curl to get just the docker-compose.yml file out of a git repo](https://github.com/docker/compose/pull/5441#issuecomment-365740221).  To get the url of the individual file, siply view it in raw mode in GitHub.  I'm using curl natively, but [he also reminds us](https://github.com/docker/compose/pull/5441#issuecomment-372503247) that we can always [run curl in docker](https://hub.docker.com/r/appropriate/curl/).
