Using Github action to deploy to multiple servers

We want to achieve the following for our Laravel application artifacts:

1. Install NPM dependencies.
2. Compile CSS and Javascript assets.
3. Install Composer dependencies.
4. Archive our build and remove unnecessary data (e.g., node_modules).
5. Store our archive so we can deploy it to our servers.

Prepare release on all our servers
We want to make sure our deployments are stable and reliable, meaning we don't want one server to be updated while the second server failed. If the preparation fails on one server, we want the deployment sequence to stop.

We want the release preparation job to do the following:

1. Ensure we have a directory that holds every release.
2. Ensure we have a storage directory that shares data between releases.
3. Ensure we have a current directory that links to the active release.
4. Extract our build files into our releases directory.
