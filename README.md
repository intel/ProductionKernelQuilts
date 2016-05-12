Quilt Representation of Intel Android Weekly Builds

INTRODUCTION:

Intel makes a weekly release of its android kernel available to
customers in the form of a git branch. In order to make the changes
easier to quantify, an equivalent quilt representation of each of these
kernels is released here. The subject line of the commit can be used to
correlate the quilt representation to the separately released git source.

QUILTS:

At the top level of the project, there is a separate directory for each
of the SOC and android desserts available. In this first release, there
is just one quilt at:

uefi/cht-m1stable (CherryTrail Marshmallow release)

FILES:

Within a quilt directory, these are the files that are present:

TechnicalDebt.csv: A list of the patch files included in the current
version of the quilt, with an associated group name for each. The field
names are in the first line of the file.

TechnicalDebtSummary.csv: A list of the groups from the
TechnicalDebt.csv file, along with the patch count for each. The field
names are in the first line of the file.

ChangeReport.txt: A description of the changes from the previous weekly
build of the same kernel.

patches/: A directory the series file and patches that comprise the quilt

patches/series: A list of the patches and the order they should be
applied to create the kernel source for the weekly build. Note that the
base KERNEL_VERSION from kernel.org is specified in a comment in the
first line of the series file.

USAGE:

Look at the first line in the patches/series file to get the kernel
version, and create a source tree (using git clone or by downloading a
tar-ball). In the top level of the kernel source tree, copy the patches
directory from the ProductionKernelQuilts github project. Then use
"quilt push -a" to apply the quilt.

Please see "man quilt" for more information about the quilt command.
