# setup-maven-gh-action

* Action prepares environment for running maven project for both runners: github and selfhosted.
* Includes restoring cache before build (can be disabled by restore-cache parameter).
* Action sets AWS_REGION env variable with default: eu-west-1

```yaml
- uses: ohpensource/platform-cicd/actions/builds/setup-maven
        name: Setup maven evnironment
        with:
          java-version: 11
          restore-cache: false
          maven-aws-access-key: <<AWS_ACCESS_KEY>>
          maven-aws-secret-key: <<AWS_SECRET_KEY>>
          account-id: <<ACCOUNT_ID>>
```

# License Summary

This code is made available under the MIT license. Details [here](LICENSE).
