# Asterisk — Personal Fork

This repository is a personal fork of [Asterisk](https://github.com/asterisk/asterisk), maintained by RubenBM as an independently controlled copy of the upstream project.

The primary purpose of this fork is to maintain a reliable downstream copy of Asterisk for personal infrastructure and contingency purposes, while retaining the ability to develop, patch, or otherwise modify Asterisk if needed.

This repository is **not an official Asterisk project repository** and is not affiliated with or endorsed by the Asterisk project or Sangoma Technologies Corporation.

## Upstream

This repository is derived from the official Asterisk project:

- **Upstream:** https://github.com/asterisk/asterisk
- **Documentation:** https://docs.asterisk.org/
- **Project:** https://www.asterisk.org/

The `master` branch is intended to remain reasonably synchronized with upstream when practical.

Upstream changes may be incorporated periodically rather than continuously.

## Purpose

This fork provides:

- An independently controlled copy of the Asterisk source
- A downstream location for personal development and maintenance
- A place to retain changes that may be required by personal infrastructure
- A foundation for future patches or downstream modifications
- A contingency path should maintaining or modifying Asterisk independently become necessary

At present, there is no requirement for this repository to maintain a permanent downstream patch set.

Substantial or reusable modifications may instead be developed in separate branches or repositories as appropriate.

## Asterisk

Asterisk is an open source PBX and telephony toolkit providing a framework for building communications applications.

For complete information about Asterisk, including supported functionality, configuration, administration, and development, refer to the official Asterisk documentation.

## Security

Read and understand the Asterisk security documentation before configuring or operating an Asterisk system.

See [`SECURITY.md`](SECURITY.md) and the official [Asterisk security documentation](https://docs.asterisk.org/).

Particular attention should be given to:

- Network exposure
- SIP/PJSIP configuration
- Authentication and authorization
- TLS and certificates
- Firewall policy
- Dialplan security
- Management interfaces
- Operating-system security
- Updates and vulnerability remediation

## Building Asterisk

Asterisk is developed and tested primarily on GNU/Linux.

Build requirements and supported platforms vary by Asterisk release. Refer to the documentation for the specific version being built rather than relying on historical compiler or operating-system requirements.

### Prerequisites

Asterisk provides a prerequisite installation script for supported systems:

    ./contrib/scripts/install_prereq test

To install the available prerequisites:

    ./contrib/scripts/install_prereq install

After installing dependencies, run `configure` again.

The prerequisite script may install dependencies for a broad range of Asterisk functionality. Review its behavior and your distribution's package requirements before using it on a production system.

### Configure

    ./configure

Review any errors or missing dependencies reported by the configuration process.

### Select Modules

Use `menuselect` to review available modules and their dependencies:

    make menuselect

### Build

    make

### Install

    make install

For a new/test installation, sample configuration files can optionally be installed with:

    make samples

**Warning:** `make samples` installs sample configuration files and may overwrite existing configuration files.

### Run

For an initial foreground test:

    asterisk -vvvc

This starts Asterisk in the foreground and provides the Asterisk CLI.

## System Configuration

Asterisk depends on appropriate operating-system configuration in addition to its own configuration.

Depending on the deployment, this may include:

- Accurate system time
- Appropriate resource limits
- Network and firewall configuration
- DNS
- TLS certificates
- User and group permissions
- Storage
- Logging
- Service supervision
- Backup and recovery

Resource requirements depend on the selected modules, configuration, traffic, and workload. Historical rules of thumb should not be treated as fixed capacity requirements.

Refer to the documentation for the Asterisk release and operating system being deployed.

## Configuration

Asterisk configuration files are normally located under:

    /etc/asterisk/

The required configuration depends on the modules, endpoints, applications, integrations, and deployment.

Sample configuration files are useful references but should not be treated as production configurations without review.

## Keeping the Fork Current

The upstream Asterisk repository is the authoritative source for the Asterisk project.

A typical synchronization workflow is:

    git remote add upstream https://github.com/asterisk/asterisk.git
    git fetch upstream
    git checkout master
    git merge upstream/master

The exact synchronization method may vary depending on downstream work.

Changes specific to this fork should generally be kept separate from the upstream-tracking branch whenever practical.

## Downstream Development

Future downstream work may include patches, integrations, configuration-related changes, experiments, or other modifications required by personal infrastructure.

There is intentionally no permanent downstream patch structure at this time.

If the fork develops substantial divergence from upstream, the repository structure and documentation will be updated accordingly.

## Documentation

The upstream Asterisk documentation remains the primary technical reference for:

- Installation
- System requirements
- Configuration
- Dialplan
- PJSIP
- Security
- APIs
- Modules
- Administration
- Troubleshooting
- Version-specific behavior

See:

- https://docs.asterisk.org/
- https://www.asterisk.org/

## Relationship to Home Infrastructure

This repository is maintained as a standalone software repository.

Asterisk may be used as part of my broader home production infrastructure, but deployment-specific configuration, infrastructure-as-code, networking, monitoring, backups, and related operational documentation belong in the corresponding infrastructure projects rather than here.

This separation keeps the Asterisk source fork reusable and prevents infrastructure-specific configuration from becoming coupled to the upstream source tree.

## Licensing and Attribution

Asterisk is free and open source software.

This repository retains the upstream Asterisk licensing, copyright, authorship, and attribution information.

See [`LICENSE`](LICENSE), [`COPYING`](COPYING), [`CREDITS`](CREDITS), and the upstream project documentation for applicable licensing and attribution information.

Asterisk and related marks are trademarks of Sangoma Technologies Corporation.

This repository is an independent personal fork and is not affiliated with, endorsed by, or operated by Sangoma Technologies Corporation or the official Asterisk project.

## Acknowledgments

This repository is based on the Asterisk project and incorporates the work of its contributors.

Original Asterisk authorship, copyright, licensing, and attribution remain applicable to the upstream code contained in this repository.

---

**Personal downstream fork of Asterisk.**

For authoritative project information and technical documentation, refer to the official Asterisk project.
