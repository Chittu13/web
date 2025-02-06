```bash

GET /api_v1/messages?user_id=ANOTHER_USERS_ID__

Try this:

GET /api_v1/messages?user_id=YOUR_USER_ID&user_id=ANOTHER_USERS_ID

Or this:

GET /api_v1/messages?user_id=ANOTHER_USERS_ID&user_id=YOUR_USER_ID

Or provide the parameters as a list:

GET /api_v1/messages?user_ids[]=YOUR_USER_ID&user_ids[]=ANOTHER_USERS_ID
```
