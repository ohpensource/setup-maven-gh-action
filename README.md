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

---

## You want to improve this GH action?

If you want to introduce changes in this solution, those will be tested in the step `test-main-script` at (.github/workflows/ci.yml)[.github/workflows/ci.yml] when you create a PR:

```yml
  test-main-script:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0
      - name: Execute script
        run: ./run-dotnet-build.sh "test-gh-action"
```

There is a dotnet solution in the `test-gh-action` folder for testing purposes.
