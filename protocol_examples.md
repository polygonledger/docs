# Protocol examples

## universal login

draft

A user goes to a website. He does not have any account with the website.

The user can key-exchange with the server without prior engagement.

{:REQ NEWUSER_CHALLENGE :pubkey xyz}

{:REP NEWUSER_CHALLENGE :challenge abc}

{:REPQ NEWUSER_CHALLENGE_RESPONSE :signature def}