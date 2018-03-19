# Innovations Traffic Light

![](https://openclipart.org/image/300px/svg_to_png/195159/Traffic-light-icon.png&disposition=attachment)

Simple bash script for changing light sequences on the traffic light in the Innovations office. This script was developed for inclusion in the [Atlassian Default Image for AWS ECS](https://bitbucket.org/teamsystems/atlassian-default-image-for-aws-ecs/src/master/) used by the RapidRecon team for their deployments. 

Required arguments:
* `-d | --data`           Payload. The request to pass to the traffic light.
* `-k | --api-key`        API Key. The key needed to authenticate the request. May also be set by  TRAFFIC_LIGHT_API_KEY environment variable. This environment variable is globally set on the Birchwood Bitbucket team for all Pipelines, so there is no need to pass this manually with your builds.

Optional arguments:
* `-u | --url`            The URL endpoint to control the traffic light.
* `-m | --method`         The action to trigger on the traffic light. 
* `--version`        Display the version of this script

Requirements:
*    `curl`  curl is a tool to transfer data from or to a server.

## Examples:
Simple way to set sequences on the traffic light:
```
# Green
traffic-light -d '{"ryg": "001"}'
# Red and Yellow
traffic-light -d '{"ryg": "110"}'
# Yellow
traffic-light -d '{"ryg": "010"}'
```
**Note:** The traffic light can be any combination of colors, it's not limited to one.

All options:
```
traffic-light --api-key V2Gsc3oseW79 -u https://traffic-light.example.ca/v1/ -m setryg --data '{"ryg": "011"}'
``` 

## License
MIT