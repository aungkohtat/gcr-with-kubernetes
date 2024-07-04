# gcr-with-kubernetes
This project demonstrates how to use Google Container Registry (GCR) with Kubernetes.
## About container service in GCP 

- **Artifact Registry:** This is the current and recommended service for managing container images and other artifacts in GCP. It provides functionalities similar to the older GCR but with additional features.
- **GCR (Google Container Registry):** While not entirely deprecated, GCR refers to the original container image registry service offered by Google Cloud Platform. It's generally recommended to migrate to Artifact Registry for its wider range of capabilities.

**Benefits of Using Artifact Registry:**

- **Centralized Management:** Manage container images alongside other development artifacts in a single location.
- **Improved Security:** Granular access controls for different artifact types based on IAM roles.
- **Versioning and Lifecycle Management:** Track different versions of artifacts and define lifecycle policies for automated management.
- **Enhanced Workflow Integration:** Integrate Artifact Registry with other GCP services and CI/CD pipelines for a smoother development workflow.

**In summary, Artifact Registry is the recommended and future-proof approach for managing container images and other artifacts in Google Cloud Platform. It supersedes the functionalities of the legacy GCR service while offering additional features and a more comprehensive management experience.**

```
I will use Artifact Registry in this lab.
```

## Setup GCP

Install Google Cloud SDK

https://cloud.google.com/sdk/docs/install#linux

When you type below command to login in from VM,you will get browser url.
Access it and get key and then paste those key on login process.
Done!

## To download the Linux archive file, run the following command:

```bash
curl -O https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-linux-x86_64.tar.gz
```

## To extract the contents of the file to your file system (preferably to your home directory), run the following command:

```bash
tar -xf google-cloud-cli-linux-x86_64.tar.gz
```

## Add the gcloud CLI to your path. Run the installation script from the root of the folder you extracted to using the following command:

```
./google-cloud-sdk/install.sh
```

## To view the available flags, run:

```
./google-cloud-sdk/install.sh --help
```

## To initialize the gcloud CLI, run gcloud init:

```bash
./google-cloud-sdk/bin/gcloud init
```

```bash
# Download the Google Cloud SDK
curl -O https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-sdk-VERSION-linux-x86_64.tar.gz

# Extract the archive
tar -xf google-cloud-sdk-VERSION-linux-x86_64.tar.gz

# Run the installation script
./google-cloud-sdk/install.sh
```
```bash
./google-cloud-sdk/bin/gcloud init
```

```bash
export PATH=$PATH:/path/to/google-cloud-sdk/bin
```

```
source ~/.bashrc
```

```
gcloud projects list
```

```
gcloud --version
```

## Create Google Cloud Artifact Registry (GCAR)  By Command

```bash
vagrant@cloud-native-box:~/gcr-with-kubernetes$ gcloud projects list
PROJECT_ID             NAME              PROJECT_NUMBER
micro-store-426307-u5  My First Project  712406925782
vagrant@cloud-native-box:~/gcr-with-kubernetes$ 
```

## If you have multiple project, you can set target project

```
gcloud config set project $PROJECT_ID
```

