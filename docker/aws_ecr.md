# AWS ECR

1.- First Configure aws-cli
2.- in ~/.aws/credential

```
[default]
aws_access_key_id = XXXXXXXX
aws_secret_access_key = XXXXXXX

```

3.- in ~/.aws/config set up the region you want to use

```
[default]
region = eu-central-1
output = json

[profile clarity-dev]
region=eu-central-1
source_profile = default
output=json

```


4.- Login in AWS ECR 

    aws  ecr get-login -region eu-west-1 --no-include-email

this return something like

```
docker login -u AWS -p eyJwYXlsb2FkIjoiNk8zelh0YkNWTFpkbFhEMzNKSDA3Y2U2WjdadWNNdnZnZURJa1FVZWNFU2xBQlROQ05HSk41RkJoVXdkS2pzTEIvcTJXeWtYSnZPek1WNXZwSGgzM2xRVUlGUnJtQnIvSzBld05nVUNhWW5oVmYwd2dQb0w0NzVCckdBcVU4dW0vU25YRDViUjVPVmZFUVNxVm55Zm1XOVZEZUxGUUdmTGVuYzVQc0t2bEJHcm5CUDlRc2JLRjltaGZmK25sd1dpSzl6NVlyZDZDWXdPdGxBVXRrTVFic1pucjdubkRlZjM5V25mSDZCWHJVOFRzMTBGVE5lUDI3MFNJQ1lFclFaWndzUTQwTFltaEl3WTZiRHBPWnB1ZEc2TnpFTEgveGpCSUsxTU1uQ0tLZndCUUVRRjBQMEg1TUgxbkVNZU5IMlNlTnVmQzAxU2JxUmFsOW1KZCtHelNWVm5rUW5NeU1tNEF1anQ2VHNYK296OW9KVTRVQk9wa1RKMXJUcWdGbmprbkdVUjVjaGhxMmlvK3REVGI2NDhQYWFFMnM2RHZOMjNjekZFeTdsdEROL29iWnBPY01RYmtsWlVIS2NBbkFGbmZvVHJmWlFhRjZXK2RZaUpIdnMvZTFMc2FxKzM5YmxqM250VWJjdnJ3TGdlcmNtRVY5c0JldWhyRWp2SkNQUmt4SitIUWFjVXUrQVRIV1RXdDZwWWc5c0ltL2JpUGhCcW1VUHVobUhJSXdMTWFCUUF1YjhWSEh5U203ZzAyYzZHeXlTZVJwN3NBRjJ5akhRcnlObDEvbnBZUkVlUmFndUlYMEZjeFB6aUdWOFpMc3ZISS84QjNXN0dsU3RnM2NiZFM4d1hHUW9YZFZvVGk2OXhsK3UyeUxpQjU0cjJFVC82emd4czhhRXdxcG5EL21hVDhIaWozUWhVaTQrWXNhcEIwSmZ5TXhhWHVEZzM4T25Lc2RzV2IvZEFtd29nbW42c2VzL29oN0xuM1hUa1JwOWF6azFzeTRuRGpBMm5WdmF5NmxvODl6cE1BN3dMaFp4RDk3aFJQV2l0SksvbUxSTG8rOTl4WDZOa2F0Umk2dytHVlNCQ1RIaWdTRlE1NFFzVE1pU0JpOEV2TnQyZ200NzRpZHcwUnZPai9PTG1mbmQ5RGk3K0dCNWt4RGxwMGd1OW5OTG1RN1ZEM1JJV3hGV2dmU1NKWURjNktOMytpNGF6K1ZqbGpnUWZ6NGxybkMwaXh2Nk9xREd1Zi80RnJ0RTE1bDYyU1pLZ3lwd3g2VUQ0NFUvekhOQ0N6eUdIaTY1bXZmZnJNdTR5KzRDN2dra3BzMmxBVEVVaXFYT09VZU9RdFZ1RjkyMkc5dmRjMitUSWJneTZZZWg5ZG8rN1RITXkrNy9yU0lrZnltNHlCZ3M1L0VRYUlhd0NoVitRU2wxZHNsNmRwODJTbjBqclBlZlhKREtsWU45aUwvZXJJYnpiczhRM1NQUlpMV1BjZ1lBeG4rVXlKTWc9IiwiZGF0YWtleSI6IkFRRUJBSGgzellPZHRwQkJTVncvWTJhbjhCWElENGt3TFFmbm9UajV6d1p0R0pab1pRQUFBSDR3ZkFZSktvWklodmNOQVFjR29HOHdiUUlCQURCb0Jna3Foa2lHOXcwQkJ3RXdIZ1lKWUlaSUFXVURCQUV1TUJFRURJN2FCUzE0bDVQbU9aQ1pEZ0lCRUlBN0RyR3cxTkpKTnF6Q2Z1Y3FpV1Vvc2NYamdXZkRIRXlSQjcydk5zMG9GcjR6cS9oTHk5ZjU5cUI0OUNNSmNVcEZPdEFGYk5oVXFMRFk5ekk9IiwidmVyc2lvbiI6IjIiLCJ0eXBlIjoiREFUQV9LRVkiLCJleHBpcmF0aW9uIjoxNTcxNzgxNTYzfQ== https://064436394451.dkr.ecr.eu-central-1.amazonaws.com
```

Copy and run the output or

    eval $(aws ecr get-login -region eu-west-1 --no-include-email)



    
## Push Docker to repo

   [https://docs.docker.com/engine/reference/commandline/push/](https://docs.docker.com/engine/reference/commandline/push/)
   
   
    docker tag kidm:latest joaquindiez75/kidm:0.1.0-SNAPSHOT
    docker push joaquindiez75/kidm:0.1.0-SNAPSHOT
   
    docker tag local-image:tagname new-repo:tagname
    docker push new-repo:tagname
    