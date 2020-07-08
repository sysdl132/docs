Gitpod IDE
===========

The following are installation instructions for the [Gitpod](https://gitpod.io/) web based IDE.

**Step 1:** Clone NodeBB into a new workspace from GitHub. Use this link:

```
https://gitpod.io/#https://github.com/NodeBB/NodeBB.git nodebb
```

The nodebb command after the git url will create a folder called nodebb
so you have to `cd` into that directory after you have cloned NodeBB.

**Step 2:** Install redis with Gitpod's package manager

```
brew install redis    # Don't use with sudo!
```

**Step 3:** Run your redis server on port 16379 - port 16379 tends to be
already used on Gitpod. 
```
redis-server --port 16379
```

**Step 4:** Run the nodebb setup utility:

```
node app --setup
```

URL of this installation should be set to
'<https://[port]-[workspace_uid].ws-us02.gitpod.io>'

Port number isn't so important - Cloud9 may force you to use port 80
anyway. Just set it to 80. If this is another port, like 4567, that is
also fine.

Use a port number to access NodeBB? Again, this doesn't seem to make a
big difference. Set this to no. Either will work.

Host port of your Redis instance: 16379

Redis Password: Unless you have set one manually, Redis will be
configured without a password. Leave this blank and press enter

First-time set-up will also require an Admin name, email address and
password to be set.

And you're good to go! Don't use the Run button at the top if the IDE,
it has been a little buggy for me. Besides, you're better off using the
command line anyway. Run:

```
node app
```

And then open <https://[port]-[workspace_uid].ws-us02.gitpod.io> in your browser.

Troubleshooting
---------------

A common problem is that the database hasn't been started. Make sure you
have set Redis up correctly and ran

```
redis-server --port 16379
```
