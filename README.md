# What is this?

It shows how you can cherry pick directories out of git repos for your own images without cloning those repos anywhere but directly into your image when you build it.

It's like [Jumping Jack](https://github.com/andrewspringman/jumpingJack) except...

I made my own image based on nginx:alpine.  It changes the working directory to the directory from which the website will be served.  It also has git installed.  The Dockerfiles use my image instead of installing git at build time.  This means it won't break if git changes or the update software changes.

I'm running the code that these Dockerfiles put in the images with no volumes mapped, so I don't need the code locally.  The code directories the images use are in Nicholas Kajoh's Jack repo on github.

## Try it

Clone it
```shell
git clone https://github.com/andrewspringman/refJack.git
```
Spin it up
```shell
docker-compose up
```
Then browse to

- [http://localhost](http://localhost)
- [http://app.localhost](http://app.localhost)
- [http://blog.loclhost](http://blog.loclhost)
- [http://localhost:8080/dashboard/](http://localhost:8080/dashboard/)

## Credits

### Nicholas Kajoh
I really enjoyed [Nicholas Kajoh's article on running multiple apps with Docker and Traefik](https://medium.com/@nicholaskajoh/how-to-run-multiple-apps-on-one-server-using-docker-and-traefik-de3f6a5ddb4c).  He provides [a github repo of the project](https://github.com/nicholaskajoh/jack).  It provides a great starting point for learning Docker and Traefik.  This is a fork of [that repo](https://github.com/nicholaskajoh/jack).

### Josh Fox
[Josh Fox (Stack Exchange id CelticParser)](https://askubuntu.com/users/384425/celticparser) provides [a method for cloning a subtree of a repo](https://askubuntu.com/questions/460885/how-to-clone-git-repository-only-some-directories/729798#729798).
