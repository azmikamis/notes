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
### Install `ksonnet`
```
export KS_VER=0.13.1
export KSFILE_VER=ks_${KS_VER}_linux_amd64
wget -O /tmp/${KSFILE_VER}.tar.gz https://github.com/ksonnet/ksonnet/releases/download/v${KS_VER}/${KSFILE_VER}.tar.gz
tar -xvf /tmp/${KSFILE_VER}.tar.gz -C ${HOME}
mv ${HOME}/${KSFILE_VER} ${HOME}/ksonnet
rm /tmp/${KSFILE_VER}.tar.gz
export PATH=$PATH:${HOME}/ksonnet
```
