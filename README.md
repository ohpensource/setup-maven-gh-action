# setup-maven-gh-action

* Action prepares environment for running maven project for both runners: github and selfhosted.
  * Special external Maven repositories can be configured in project main pom.xml file
    * default maven version is **3.8.8**
  * setup AWS Corretto Java distribution
* Includes restoring cache before build (can be disabled by restore-cache parameter).
* Action sets AWS_REGION env variable with default: eu-west-1

```yaml
      - uses: ohpensource/setup-maven-gh-action@v0.1.0
        name: Setup maven evnironment
        with:
          java-version: 11
          restore-cache: false
          maven-aws-access-key: <<AWS_ACCESS_KEY>>
          maven-aws-secret-key: <<AWS_SECRET_KEY>>
          account-id: <<ACCOUNT_ID>>
```

**Note:** 

This action: [https://github.com/skjolber/maven-cache-github-action] was replaced by equivalent fork with fixed
deprecated GitHub commands and node version. If original repo action will be fixed, we can move to new version.

# License Summary

This code is made available under the MIT license. Details [here](LICENSE).
