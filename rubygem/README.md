```bash

# USERNAME=bob
RELEASE_BRANCH="master"
GIT_REMOTE="upstream"
```

#
# Checking out version to release
#
git fetch $GIT_REMOTE
git checkout $GIT_REMOTE/$RELEASE_BRANCH

#
# Creating a new gem
#
bundle gem cookinator

#
# Grabbing rubygems authentication token
#
curl -u $USERNAME https://rubygems.org/api/v1/api_key.yaml > ~/.gem/credentials; chmod 0600 ~/.gem/credentials
Enter host password for user 'bob':
cat ~/.gem/credentials
---
:rubygems_api_key: *********************************

```
