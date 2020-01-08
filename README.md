# Meteor 1.8.3, rebuild issue [#10591](https://github.com/meteor/meteor/issues/10591)

This repo is there to support Meteor issue: [#10591](https://github.com/meteor/meteor/issues/10591)


To recreate this repo from scratch:

```
meteor create meteor-rebuild-issue --release 1.8.3 --react
cd meteor-rebuild-issue
meteor
```

Now edit `./imports/ui/Hello.jsx`, and notice that only the client bundle is being rebuild.

Next, rename `./imports` to `./common`, and update the import statement in `./client/main.jsx` and `./server/main.js` to reflect the new path. Wait for the application to rebuild.

Now, go ahead and change something in `./common/ui/Hello.jsx`.

You'll notice that the server is rebuild as well, while changes inside the imports directory did not.
