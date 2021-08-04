docker build . --no-cache -t lucas:latest
docker run -p 8051:8000 -it --volume=`pwd`:/usr/src/app lucas:latest bash
docker run -p 8051:8000 lucas:latest