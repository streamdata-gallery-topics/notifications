---
swagger: "2.0"
x-collection-name: GitHub
x-complete: 0
info:
  title: Github Get Repos Owner Repo Notifications
  description: |-
    List your notifications in a repository
    List all notifications for the current user.
  termsOfService: https://help.github.com/articles/github-terms-of-service/#b-api-terms
  version: 1.0.0
host: api.github.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /notifications:
    get:
      summary: Get Notifications
      description: |-
        List your notifications.
        List all notifications for the current user, grouped by repository.
      operationId: list-your-notificationslist-all-notifications-for-the-current-user-grouped-by-repository
      x-api-path-slug: notifications-get
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: query
        name: all
        description: True to show notifications marked as read
      - in: query
        name: participating
        description: True to show only notifications in which the user is directly
          participatingor mentioned
      - in: query
        name: since
        description: 'The time should be passed in as UTC in the ISO 8601 format:
          YYYY-MM-DDTHH:MM:SSZ'
      responses:
        200:
          description: OK
      tags:
      - Notifications
    put:
      summary: Put Notifications
      description: |-
        Mark as read.
        Marking a notification as "read" removes it from the default view on GitHub.com.
      operationId: mark-as-readmarking-a-notification-as-read-removes-it-from-the-default-view-on-githubcom
      x-api-path-slug: notifications-put
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Notifications
  /notifications/threads/{id}:
    get:
      summary: Get Notifications Threads
      description: View a single thread.
      operationId: view-a-single-thread
      x-api-path-slug: notificationsthreadsid-get
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: path
        name: id
        description: Id of thread
      responses:
        200:
          description: OK
      tags:
      - Notifications
      - Threads
    patch:
      summary: Patch Notifications Threads
      description: Mark a thread as read
      operationId: mark-a-thread-as-read
      x-api-path-slug: notificationsthreadsid-patch
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: path
        name: id
        description: Id of thread
      responses:
        200:
          description: OK
      tags:
      - Notifications
      - Threads
  /notifications/threads/{id}/subscription:
    delete:
      summary: Delete Notifications Threads  Subscription
      description: Delete a Thread Subscription.
      operationId: delete-a-thread-subscription
      x-api-path-slug: notificationsthreadsidsubscription-delete
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: path
        name: id
        description: Id of thread
      responses:
        200:
          description: OK
      tags:
      - Notifications
      - Threads
      - ""
      - Subscription
    get:
      summary: Get Notifications Threads  Subscription
      description: Get a Thread Subscription.
      operationId: get-a-thread-subscription
      x-api-path-slug: notificationsthreadsidsubscription-get
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: path
        name: id
        description: Id of thread
      responses:
        200:
          description: OK
      tags:
      - Notifications
      - Threads
      - ""
      - Subscription
    put:
      summary: Put Notifications Threads  Subscription
      description: |-
        Set a Thread Subscription.
        This lets you subscribe to a thread, or ignore it. Subscribing to a thread
        is unnecessary if the user is already subscribed to the repository. Ignoring
        a thread will mute all future notifications (until you comment or get @mentioned).
      operationId: set-a-thread-subscriptionthis-lets-you-subscribe-to-a-thread-or-ignore-it-subscribing-to-a-threadis-
      x-api-path-slug: notificationsthreadsidsubscription-put
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: Id of thread
      responses:
        200:
          description: OK
      tags:
      - Notifications
      - Threads
      - ""
      - Subscription
  /repos/{owner}/{repo}/notifications:
    get:
      summary: Get Repos Owner Repo Notifications
      description: |-
        List your notifications in a repository
        List all notifications for the current user.
      operationId: list-your-notifications-in-a-repositorylist-all-notifications-for-the-current-user
      x-api-path-slug: reposownerreponotifications-get
      parameters:
      - in: header
        name: Accept
        description: Is used to set specified media type
      - in: query
        name: access_token
        description: Your Github OAuth token
      - in: query
        name: all
        description: True to show notifications marked as read
      - in: path
        name: owner
        description: Name of repository owner
      - in: query
        name: participating
        description: True to show only notifications in which the user is directly
          participatingor mentioned
      - in: path
        name: repo
        description: Name of repository
      - in: query
        name: since
        description: 'The time should be passed in as UTC in the ISO 8601 format:
          YYYY-MM-DDTHH:MM:SSZ'
      responses:
        200:
          description: OK
      tags:
      - Repos
      - Owner
      - Repo
      - Notifications
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