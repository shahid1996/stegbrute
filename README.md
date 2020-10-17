![](https://api.travis-ci.org/R4yGM/StegBrute.svg)
# stegbrute
stegbrute is a steganography brute-force tool written in Rust to achieve a faster execution using also threads

<p align="center">
  <img src="https://i.imgur.com/zGFolUt.png" >
</p>


# Installation
stegbrute can be installed in different ways:

## **Cargo**

<img src="https://community.kde.org/images.community/thumb/5/5e/Rust-logo-512x512-blk.png/300px-Rust-logo-512x512-blk.png" width=35 height=35>

 throught [cargo](https://github.com/rust-lang/cargo) (Rust package manager)
 
 if you don't have cargo you can install it either from apt or by downloading Rust lang
```bash
cargo install stegbrute
```
**this will work for every platform**

## **Docker**

<img src="https://cdn3.iconfinder.com/data/icons/logos-and-brands-adobe/512/97_Docker-512.png" width=35 height=35>

  if you don't have docker installed you can follow their [guide](https://docs.docker.com/engine/install/)
  
 first you have to pull the docker image (only **4.93 MB**) from the docker registry, you can see it [here](https://hub.docker.com/r/r4yan/stegbrute), if you don't want to pull the image you can also clone the repository and then build the image from the Dockerfile
 ```bash
docker pull r4yan/stegbrute:latest
  ```
  you can also decide to pull different images by replacing 'latest' with a stegbrute version, ex.
  ```bash
docker pull r4yan/stegbrute:0.1.0
  ```
  
  if you don't want to pull the image you can download/copy stegbrute Dockerfile that can be found [here](https://github.com/R4yGM/stegbrute/blob/main/Dockerfile) and then build the image from the Dockerfile
  
  then if you want to launch the container you have to first create a volume to share your files to the container
  
  ```bash
  docker volume create --name stegbrute_data
  ``` 
  then move or copy the files you want to use for stegbrute inside the volume folder wich usually is here `/var/lib/docker/volumes/stegbrute_data/_data` by just doing
  ```bash
  cp wordlist.txt /var/lib/docker/volumes/stegbrute_data/_data && cp file.jpg /var/lib/docker/volumes/stegbrute_data/_data
  ```
  and now run stegbrute
  ```bash
  docker run -v stegbrute_data:/stegbrute_data -it --rm --name stegbrute r4yan/stegbrute:latest <options>
  ```
  replace the `<options>` with the options/arguments you want to give to stegbrute,
  once you did everything you don't have to pull/build the image again only if there are new updates or features
  
  **Always save your results inside the volume and not in the container because then the results will be deleted! you can save them by adding this option `-x /$VOLUME_NAME/results.txt` or `--extract-file /$VOLUME_NAME/results.txt`** 
 
 if you added this and did everything correctly at the end of every attack you'd find the results inside the folder `/var/lib/docker/volumes/stegbrute_data/_data`
  
  
  **this will work for every platform**
# Usage
