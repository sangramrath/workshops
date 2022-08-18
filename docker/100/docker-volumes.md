    1  clear
    2  docker run -it --name busybox-c1 -v /data busybox sh
    3  docker ps
    4  clear
    5  docker volume ls
    6  docker volume inspect e4d864889712a674cfd29a7943538d1bd56898524cd8c62cdc50fa3734b1e414
    7  ls -l /var/lib/docker/volumes/e4d864889712a674cfd29a7943538d1bd56898524cd8c62cdc50fa3734b1e414/_data
    8  ls -l  /var/lib/docker/volumes/
    9  clear
   10  clear
   11  docker run -it --name busybox-c2 --volumes-from busybox-c1 busybox sh
   12  docker volumes ls
   13  docker volume ls
   14  docker ps -a
   15  docker rm busybox-c1
   16  docker volume ls
   17  docker rm busybox-c2
   18  docker volume ls
   19  clear
   20  docker volume create datavol
   21  docker volume ls
   22  docker run -d --name busybox-named -v datavol:/datavol busybox sh
   23  docker docker volume inspect datavol
   24  docker volume inspect datavol
   25  docker ps
   26  docker run -it --name busybox-named -v datavol:/datavol busybox sh
   27  docker run -it --name busybox-c3 -v datavol:/datavol busybox sh
   28  docker rm busybox-c3
   29  docker run -it --name busybox-c4 -v datavol:/datavol busybox sh
   30  docker ps -a
   31  docker rm busybox-c4
   32  docker rm busybox-named
   33  docker run -it --name busybox-c5 -v datavol:/datavol busybox sh
   34  clear
   35  docker volume create --opt o=size=500m,uid=1000
   36  docker volume create --driver local --opt o=size=500m,uid=1000
   37  docker volume create --help
   38  docker volume create --opt --help
   39  clear
   40  docker volume create --driver local --opt size=500m,uid=1000 fixed-size
   41  docker volume create --driver local --opt size=500m fixed-size
   42  docker volume ls
   43  docker volume inspect fixed-size
   44  clear
   45  docker volume create --driver local --opt type=tmpfs --opt device=tmpfs --opt o=size=10m,uid=1000 tmpze=10m,uid=1000 tmpfs
   46  docker volume create --driver local --opt type=tmpfs --opt device=tmpfs --opt o=size=10m,uid=1000 tmpclear tmpfs
   47  clear
   48  clear
   49  docker volume create --driver local --opt type=tmpfs --opt device=tmpfs --opt o=size=10m,uid=1000 tmpfs
   50  clear
   51  git clone https://github.com/sangramrath/vCard
   52  ls -l 
   53  docker run -d -p 80:80 --name vcard -v $(pwd)/vCard:/usr/share/nginx/html/ nginx 
   54  docker ps 
   55  cd vCard/
   56  vi index.html 
   57  vi index.html 
   58  vi index.html 
   59  clear
   60  cd 
   61  docker ps
   62  docker exec -it vcard bash
   63  docker commit 3e37a887a42b nginx:v1
   64  docker images
   65  docker run -d --name nginxv1 nginx:v1
   66  docker ps
   67  docker exec -it c6cd79be2310 bash
   68  history > history_volume_operation
