---
title: runC FAQ
---

## FAQ

### License

runC is free software, licensed under the [Apache 2.0 license][license] (as are all [OCI projects][oci]).
The source code is hosted on [GitHub][source].

### Reporting Bugs

If you've found a security issue, please **do not** submit a bug on our public bug tracker.
Instead, please send an email to [security@opencontainers.org][security-ml] with a clear description of the problem (preferably with a proof-of-concept).
We will work with you to confirm the severity of the security issue, write and approve a patch, as well as send alerts to distributions.

Otherwise, please submit a descriptive bug report to [our bug tracker][bugs].
It is preferred if the bug is reproducible, and if you provide information on your local environment.

### Feature Requests

As with bugs, please submit a detailed feature request to [our bug tracker][bugs].
It is recommended that the request be phrased as a proposal, with details about the reason for the feature and how it would be implemented.

### Sending Patches

We use [GitHub's pull request system][pulls] for reviewing and merging patches.
If your patch implements some significant functionality, or fixes a regression, please add appropriate unit or integration tests.
All patches submitted must undergo review by two maintainers of the project before being merged, so please be patient.
For more information, read the [`CONTRIBUTING.md`][contributing] file in the root of the runC source code.

[oci]: https://github.com/opencontainers
[license]: https://github.com/opencontainers/runc/blob/master/LICENSE
[source]: https://github.com/opencontainers/runc
[security-ml]: mailto:security@opencontainers.org
[bugs]: https://github.com/opencontainers/runc/issues
[pulls]: https://github.com/opencontainers/runc/pulls
[contributing]: https://github.com/opencontainers/runc/blob/master/CONTRIBUTING.md
