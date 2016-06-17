# Disconnection and Dropout

Users may disconnect and reconnect to your experiment, or leave without 
coming back. A good experiment design accounts for this and minimizes the 
disruption to other users and the quality of the data.

### Connection Issues:

- Your project code should keep tabs on the connection state of each user and should have some kind of connection timer that prevents one user from getting "stuck" if their partner(s) disconnect
- Likewise if rematching users is important, make sure to build that into your project code and critically set it up in a way that your Assigner knows what to do, for example:
- An Assigner that uses number of instances and a boolean flag to properly route users:
    - When a user hits the TS Lobby the assigner checks if they have been in any experiment instances
    - If they have, it looks for a rematch boolean flag and if it sees it, leaves them in the lobby to get matched again
    - If it doesn't see that flag it assumes they have completed their experiment instance and pushes them to the TS Exit survey 
    - If it doesn't see any experiment instances it assumes this is their first time in the lobby and leaves them there to get matched 

### Idling Issues:

- Your project should probably deal with users that take exceedingly long to respond
- One solution is to setup the Assignment duration so that that a user must complete it within a certain time otherwise risk being unable to submit
    - This can be problematic if one user *causes* another user to lose out on the opportunity to submit the HIT because they themselves took too long
- Another solution is to track the idle state of a user through Turkserver and start a forced disconnect if a user has been idling too long
    - This is tricky to setup, but more ideal because users can be handled independently of each other, e.g.
        - If user A idles and is force disconnected, user B can simply be rematched or pushed to the end of the of experiment 
