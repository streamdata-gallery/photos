---
swagger: "2.0"
info:
  title: Meetup Group Venues
  description: Returns venues a group has previously hosted events at
  version: 1.0.0
host: api.meetup.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /:urlname/venues:
    get:
      summary: Group Venues
      description: Returns venues a group has previously hosted events at
      operationId: venues
      parameters:
      - in: query
        name: fields
        description: Comma-delimited list of optional fields to append to the response
        type: string
      responses:
        200:
          description: OK
      tags:
      - events
      - photos
      - veues
definitions: []
x-collection-name: Meetup
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---