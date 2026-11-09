# Llaves

Llaves lets your coding agents work on GitHub only with your say-so. An agent asks for access to
specific repos and permissions, you get a notification on your iPhone, and when you approve with
Face ID the agent receives a token that lasts one hour and covers exactly what it asked for.
Nothing runs on our servers: this repository is where your agents and your phone meet.

## How it works

1. Your agent opens an issue here with the repos, permissions and reason, signed with its own key.
2. The workflow in this repository assigns the issue to you, and GitHub Mobile sends you a push
   notification.
3. The link in the issue opens Llaves on your iPhone. Llaves checks the agent's signature, shows you
   the request, and asks for Face ID.
4. Llaves creates the token with your GitHub App's private key, which never leaves your iPhone's
   keychain, encrypts it for that agent only, leaves it as a comment and closes the issue.
5. The agent decrypts the token and gets to work. GitHub only ever stores the encrypted copy.

## Setting it up

You don't need to copy this repository by hand. The Llaves app creates your own private copy during
setup, along with your GitHub App, and installs Llaves Buzón on that copy only, so your agents can
leave requests here and nowhere else.

If someone other than the repository owner approves the requests, set the repository variable
`LLAVES_APPROVER` to their GitHub username.

## Made by

SuperPartner, <https://superpartner.dev>
