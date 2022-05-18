### Export Docker Image as a tar archive
```
docker save -o mydockerimage.tar [DOCKERIMAGENAME]
```
### Import Docker Image tar archive
```
docker load -i mydockerimage.tar 
```
### Verify
```
docker images
```