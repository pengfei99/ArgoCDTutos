# ArgoCDTutos

## 0. Pre requise

### 0.1 Kustomize
Kustomize, at it’s core, is meant to build native Kubernetes manifests based on YAML, while leaving the original 
YAML intact. It achieves this in a "template-less" templating format. This is done by providing a **kustomization.yaml** file.

#### Install kustomize

Step1 : Download the binary

```shell
# create a dir to store the bin of kustomize
mkdir -p /opt/kustomize/bin

# goto the dir
cd /opt/kustomize/bin

# The following script detects your OS and downloads the appropriate kustomize binary to your current working directory.
curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash

```

Step 2: create startup loaing script

```shell
sudo vim /etc/profile.d/kustomize.sh

# put the following line in it 
export KUSTOMIZE_HOME=/opt/kustomize
export PATH=$PATH:$KUSTOMIZE_HOME/bin 

# to load the path in your current terminal
source /etc/profile.d/kustomize.sh
```

Step 3: Test your kustomize bin

```shell
kustomize version --short

# output
> {kustomize/v4.4.1  2021-11-11T23:36:27Z  }

```