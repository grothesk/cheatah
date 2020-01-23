# Configuration

## Switch to Namespace permanently

Switch to another namespace permanently like this:

    kubectl config set-context $(kubectl config current-context) --namespace=my-namespace
