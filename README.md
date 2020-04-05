# OpenStack availability zone support for openshift-installer release 4.3

## For general AZ support

    git clone https://github.com/ITD27M01/openshift-installer-patchset.git
    git clone https://github.com/openshift/installer.git $GOPATH/src/github.com/openshift/installer
    cd $GOPATH/src/github.com/openshift/installer
    git checkout release-4.3
    git apply ~/01_openstack_az_support.diff
    git apply ~/03_openstack_hints_router.diff
    hack/build.sh
    # OpenShift 4.3.10 image
    export OPENSHIFT_INSTALL_RELEASE_IMAGE_OVERRIDE=quay.io/openshift-release-dev/ocp-release@sha256:edb4364367cff4f751ffdc032bc830a469548f998127b523047a8dd518c472cd
    bin/openshift-installer create cluster

## For distributed router support

    git clone https://github.com/ITD27M01/openshift-installer-patchset.git
    git clone https://github.com/openshift/installer.git $GOPATH/src/github.com/openshift/installer
    cd $GOPATH/src/github.com/openshift/installer
    git checkout release-4.3
    git apply ~/01_openstack_az_support.diff
    git apply ~/03_openstack_hints_router.diff
    git apply ~/04_openstack_distributed_router.diff
    hack/build.sh
    # OpenShift 4.3.10 image
    export OPENSHIFT_INSTALL_RELEASE_IMAGE_OVERRIDE=quay.io/openshift-release-dev/ocp-release@sha256:edb4364367cff4f751ffdc032bc830a469548f998127b523047a8dd518c472cd
    bin/openshift-installer create cluster

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, TITLE AND NON-INFRINGEMENT.