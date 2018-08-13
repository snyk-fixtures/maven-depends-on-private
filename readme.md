### Overview

- the three folder are different versions of the same basic pom
- these poms should be deployed to your local Artifactory instance
- the root pom depends on version 1.0.0 (private-dep-with-vulns)
- the root pom does not explicitly specify the artifact repository that contains its dependency (forcing the "repositories" configuration to happen in the SAAS platform)

### Deploying the artifacts into Artifactory

```bash
$ cd private-dep-with-vulns
$ mvn deploy -DaltDeploymentRepository=central::default::https://artifactory.example.com/artifactory/libs-release
```

Change https://artifactory.example.com to point to the actual Artifactory instance

Repeat the above for `private-dep-with-fewer-vulns` and `private-dep-with-no-vulns`

Note: please do NOT deploy the root pom
