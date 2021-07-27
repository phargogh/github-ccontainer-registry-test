# github-ccontainer-registry-test
Can I push two images to the same container registry?

Yes.  Yes you can.  N packages can be associated with a single repository.  Very cool.
Process for getting this to work with container registry:

* Build the image locally or on github actions or wherever
* Log in to the github package repository (may require an access token, see https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry#authenticating-to-the-container-registry)
* Tag the built image with `docker tag [IMAGE] ghcr.io/[GITHUB USERNAME]/[PACKAGENAME]:[VERSION]`
* Push the new tag to`docker push ghcr.io/[GITHUB USERNAME]/[PACKAGENAME]:[VERSION]`
* The just-pushed package will be available under the "Packages" tab on  your github profile.  Click the link.  For me, this is https://github.com/phargogh?tab=packages
* Locate the package you want to associate with a repository.
* Scroll down.  Click the button to associate the package with a repository.
* Observe package is now associated with the repository.
* Done!
