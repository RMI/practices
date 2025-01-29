# Software Versioning

Versioning is a critical aspect of software development. It is the process of assigning identifiers to a collection of code to distinguish it from other versions of the same collection. In contrast to a "git hash", which serves as an immutable machine-friendly identifier of the state of the code, the version number serves to communicate the behavior of the code to humans (and especially anticipated differences from earlier versions). This document outlines our practices for versioning code.

## Semantic Versioning

Semantic versioning ([SemVer](https://semver.org/)) is a versioning scheme that provides a simple set of rules and requirements that dictate how version numbers are assigned and incremented. The version number is a three-part number in the format of `MAJOR.MINOR.PATCH`.
- `MAJOR` version increments when you make backwards-incompatible changes
- `MINOR` version increments when you add functionality in a backwards-compatible manner
- `PATCH` version increments when you make backwards-compatible bug fixes, or maintenance, upkeep or any other developer-facing improvements

When a package is in a development stage (e.g. not yet ready for release), it is identified by "adding a large component" to the version number, e.g. `0.1.0.9000`. This is a signal to users that the package is in between stable releases.

## Calender Versioning

Calender versioning (CalVer) is a versioning scheme that uses some portion of the date of release as the version number. There are different styles of CalVer. One is very similar to SemVer, however the `MAJOR` version is instead replaced with the year of release, e.g. `YYYY.MINOR.PATCH`. Other variants can be found here: [CalVer](https://calver.org/).

## R Packages

R packages should be versioned using a Semantic Versioning (SemVer) compliant variant as described in the [R package versioning guide](https://r-pkgs.org/release.html#release-version).

This means, either standard SemVer, or the CalVer variant as described above. This may be the case, for example, in packages who's primary exported outputs are data, and the package is updated on a regular schedule.

## Other Repositories

At this stage, no clear guidance is given for other `RMI` repositories. In general, some consistent tagging system may be useful (e.g. tag relevant images with `date-built`, or `COP CH 2024`, or other useful user-facing tags), but the specifics of this are left to the discretion of the repository maintainers.

## References

- [Semantic Versioning](https://semver.org/)
- [Calender Versioning](https://calver.org/)

## How

-   [R package versioning guide](https://r-pkgs.org/release.html#release-version).
