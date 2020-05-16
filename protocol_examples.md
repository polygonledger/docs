# Protocol examples

draft, work in progress

## DNS update and ipfs

Update DNS record and hook up to IPFS

{:REQ DNS_UPDATE...}

## universal login

A user goes to a website. He does not have any account with the website.

The user can key-exchange with the server without prior engagement.

{:REQ NEWUSER_CHALLENGE :pubkey xyz}

{:REP NEWUSER_CHALLENGE :challenge abc}

{:REQ NEWUSER_CHALLENGE_RESPONSE :signature def}