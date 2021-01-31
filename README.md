# What is this project?

This is RPM spec file for [OpenPBS](https://github.com/openpbs/openpbs). "OpenPBS® software optimizes job scheduling and workload management in high-performance computing (HPC) environments – clusters, clouds, and supercomputers – improving system efficiency and people’s productivity."

This spec file is derived from official spec file and twisted to fit Fedora Copr built. Some essencial changes were already merged into upstream, e.g. [pmix fix](https://github.com/openpbs/openpbs/commit/1b55d3d418c1074a6d70687d2e203ab06203f4ca).

# Is it safe?

Source files are directly fetched from [OpenPBS's releases](https://github.com/openpbs/openpbs/releases).

# What is the target version / OS?

Currently the spec targets [v20.0.1](https://github.com/openpbs/openpbs/releases/tag/v20.0.1). Please notify me if you want a new release.

CentOS7, CentOS8 and CentOS8 Stream packages were available. CentOS7 package was built without pmix support, because it lack pmix 2+.

# Any risk?

Upgrade the scheduler in productive environment is always risky. Remember to backup your ```/var/spool/pbs``` before upgrade.

# How to utilize this project?

Binary packages (as well as SRPMS) are released at [COPR](https://copr.fedorainfracloud.org/coprs/aflyhorse/openpbs/).
- ![status](https://copr.fedorainfracloud.org/coprs/aflyhorse/openpbs/package/openpbs/status_image/last_build.png)

There are 4 rpm packages in the yum / dnf repo:

- ```openpbs-client```, submit binaries, for submit node / client PC only
- ```openpbs-devel```, headers and libraries, for MPI programs like OpenMPI and MPICH / Mvapich to reference while building.
- ```openpbs-execution```, MOM for execution nodes
- ```openpbs-server```, scheduler and MOM for head nodes and standalone server

Usually, users should install ```openpbs-server``` on server nodes, and ```openpbs-execution``` on execution nodes.

# How can I report problems?

I only build official released tarballs (or officially suggested ones).

Please only contact me on packaging problems. For the others, please report to the upstream.
