---
swagger: "2.0"
x-collection-name: Meetup
x-complete: 0
info:
  title: Meetup Photos
  description: This method returns photos by member, group, album, event, photo ID,
    or tagged member.
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
  /photos:
    get:
      summary: Photos
      description: API method for accessing meetup photos
      operationId: deprecated
      x-api-path-slug: photos-get
      parameters:
      - in: query
        name: album_id
        description: return photos for the albums with the given id, separated by
          commas
        type: string
      - in: query
        name: group_id
        description: Return photos in groups with these ID numbers [separated by commas]
        type: string
      - in: query
        name: group_urlname
        description: return photos for the group with given custom URL path
        type: string
      - in: query
        name: topic
        description: Return photos in this topic
        type: string
      - in: query
        name: topic, groupnum
        description: return photos for the group with given topic and number
        type: string
      - in: query
        name: topic_id
        description: Return photos in topics with this ID number
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - Photos
  /2/photo/:id:
    delete:
      summary: Event Photo Delete
      description: Deletes a specified event photo
      operationId: photos
      x-api-path-slug: 2photoid-delete
      responses:
        200:
          description: OK
      tags:
      - Events
      - Photos
    post:
      summary: Event Photo Edit
      description: Edits a specified event photo
      operationId: photos
      x-api-path-slug: 2photoid-post
      parameters:
      - in: query
        name: caption
        description: Photo caption of up to 255 characters
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - Photos
  /2/photo_comment:
    post:
      summary: Photo Comment v2
      description: This method posts comments that appear below photos
      operationId: photos
      x-api-path-slug: 2photo-comment-post
      parameters:
      - in: query
        name: comment
        description: The comment text
        type: string
      - in: query
        name: photo_id
        description: The photo related to this comment
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - Photos
      - Comments
  /2/photo_albums:
    get:
      summary: Photo Albums
      description: This method returns photo albums associated with Meetup groups.
        To create albums, see the corresponding write method.
      operationId: photos
      x-api-path-slug: 2photo-albums-get
      parameters:
      - in: query
        name: event_id
        description: Return photo albums for these event ids, separated by commas
        type: string
      - in: query
        name: group_id
        description: Return albums in groups with these ID, separated by commas
        type: string
      - in: query
        name: photo_album_id
        description: Return albums with these IDs, separated by commas
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - Photos
      - Comments
  /2/photos:
    get:
      summary: Photos
      description: This method returns photos by member, group, album, event, photo
        ID, or tagged member.
      operationId: photos
      x-api-path-slug: 2photos-get
      parameters:
      - in: query
        name: api_version
        description: "2"
        type: string
      - in: query
        name: callback
        description: Name of a function to be called with an array of photo notification
          objects
        type: string
      - in: query
        name: event_id
        description: Limit notifications to a specific event id
        type: string
      - in: query
        name: event_id
        description: Event ids, separated by commas
        type: string
      - in: query
        name: fields
        description: comma-delimited optional response properties such as member_country,
          member_city, member_state, and self
        type: string
      - in: query
        name: group_id
        description: Group IDs, separated by commas
        type: string
      - in: query
        name: group_urlname
        description: Group urlnames, separated by commas
        type: string
      - in: query
        name: member_id
        description: Uploaded by members with these IDs, separated by commas
        type: string
      - in: query
        name: photo_album_id
        description: Photo Album IDs, separated by commas
        type: string
      - in: query
        name: photo_id
        description: Photo IDs, separated by commas
        type: string
      - in: query
        name: since_count
        description: Request that some number of recent messages be sent immediately,
          if available
        type: string
      - in: query
        name: since_mtime
        description: Should be supplied for all but the first polling request, so
          that any missed notifications are can be sent in an immediate response
        type: string
      - in: query
        name: tagged
        description: Tagged with members with these IDs, separated by commas
        type: string
      - in: query
        name: time
        description: Return photos uploaded within the given time range, defined by
          two times separated with a single comma
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - Photos
x-streamrank:
  polling_total_time_average: "0.11"
  polling_size_download_average: "13957.05"
  streaming_total_time_average: "0.06"
  streaming_size_download_average: "7006.35"
  change_yes: "29"
  change_no: "2252"
  time_percentage: "43"
  size_percentage: "50"
  change_percentage: "1"
  last_run: "2018-05-12"
  days_run: "8"
  minute_run: "0"
---