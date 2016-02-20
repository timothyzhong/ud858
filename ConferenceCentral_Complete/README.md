App Engine based Conference application

## Language
- Python

## APIs
- Google Cloud Endpoints

## Setup Instructions
1. Create a project in AppEngine Developer Console[1]
2. Download Google AppEngine launcher[2]
3. In Google AppEngine launcher, load this project. Change 'application' in
   'app.yaml' to the application ID created in step 1.
4. In Developer Console, create credentials. Update CLIENT_ID in 'settings.py'
   and 'static/js/app.js'.
5. In the launcher, run the application locally[3] or deploy to visit online[4].
6. (optional)Access API explorer[5]



[1]: https://console.developers.google.com
[2]: https://cloud.google.com/appengine/downloads
[3]: http://localhost:8080 (or what's specified in the launcher)
[4]: https://{application_ID}.appspot.com
[5]: {application_address}/_ah/api/explorer

Answers
Task1: Sessions are implemented as Session objects and have SessionForm for
       input/output. Session objects have websafeConferenceKey property. When
       a session is created, the websafeConferenceKey is entered as parent. That
       makes it easy to get all sessions in a conference.

       Speakers are implemented as a string property in Session object. So each
       session has the name of the speaker, which can be used for querying
       a session.

Task3: getSessionsByDuration allows user to provide lower bound and upper bound
       of duration and get all sessions with durations within that range.

       getSessionsByHighlight allows user to provide one or more highlights that
       he/she is interested in, and get a list of sessions that cover those
       highlights.

       querySessions allows user to query sessions combining different fields.

       Query problem: In order to achieve this function, a query that supports
       multiple multiple filters should be implemented. StartTime and typeOfSession
       should be included in the supported filters. So we can query sessions
       with startTime less than 19:00 and typeOfSession not equal to workshop.
