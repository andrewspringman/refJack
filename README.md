# What is this?

It's like [Jumping Jack](https://github.com/andrewspringman/jumpingJack) except...

I made my own image based on nginx:alpine.  It changes the working directory to the directory from which the website will be served.  It also has git installed.  The Dockerfiles use my image instead of installing git at build time.  This means it won't break if git changes or the update software changes.

I'm running the code that these Dockerfiles put in the images with no volumes mapped, so I don't need the code locally.  The code directories the images use are in a repo on github.

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
