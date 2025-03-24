## Install and configure virtualization Operator

### Install virtualization Operator

* To install the Operator using the default namespace, follow these steps:
  ```
  export CHANNEL_NAME="stable"
  export STARTING_CSV="kubevirt-hyperconverged-operator.v4.16.5"
  # export STARTING_CSV="kubevirt-hyperconverged-operator.v4.14.10"
  # export STARTING_CSV="kubevirt-hyperconverged-operator.v4.17.3"
  export CATALOG_SOURCE_NAME="redhat-operators"
  export NAMESPACE="openshift-cnv"

  curl -s https://github.com/catherine-hy/ocp/blob/main/virt/01-operator.yaml | envsubst | oc create -f -
  curl -s https://github.com/catherine-hy/ocp/blob/main/operator/approve_ip.sh | bash
  ```

### Create HyperConverged
* Create HyperConverged and Check
  ```
  oc create -f https://github.com/catherine-hy/ocp/blob/main/virt/02-hyperconverged.yaml

  oc get pod -n openshift-cnv
  ```

