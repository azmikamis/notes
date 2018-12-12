### Install `kfctl`
```
export KUBEFLOW_SRC=${HOME}/kubeflow
export KUBEFLOW_TAG=v0.3.4
mkdir -p ${KUBEFLOW_SRC}
cd ${KUBEFLOW_SRC}
curl https://raw.githubusercontent.com/kubeflow/kubeflow/${KUBEFLOW_TAG}/scripts/download.sh | bash
ln -s ${KUBEFLOW_SRC}/scripts/kfctl.sh ${KUBEFLOW_SRC}/scripts/kfctl
export PATH=${PATH}:${KUBEFLOW_SRC}/scripts
cd ~
```
