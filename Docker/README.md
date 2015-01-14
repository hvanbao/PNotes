- OpenSSH
====================
- Apache2
====================
- Supervisor: A Process Control System 
====================
* Supervisor is a client/server system that allows its users to monitor and control a number of processes on UNIX-like operating systems.
* http://supervisord.org/
* Using Supervisor with Docker: https://docs.docker.com/articles/using_supervisord/

=====================
- Run docker in deamon mode

```bash
$ which docker
$ /usr/local/bin/docker
$ sudo /usr/local/bin/docker -H 0.0.0.0:5555 -d &
```
- List all containers by Docker API

```
http://localhost:5555/containers/json
```
