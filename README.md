# docker-commands

## container로 image 생성

```
docker commit -a "jjy" {container_id} {image_name}/{image_tag}
```

>https://docs.docker.com/engine/reference/commandline/commit/
```
docker commit 548113ec4304 couchbase/test/20210121 
```

## docker image 삭제

## repository or tag가 none인 이미지 삭제

```
docker rmi $(docker images -q --filter "dangling=true")
```

## 특정키워드가 있는 이미지 삭제

```
docker rmi $(docker images --format "{{.ID}} {{.Repository}}" | grep "KEYWORD" | awk '{print $1}')
```
