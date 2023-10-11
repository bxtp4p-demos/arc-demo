# ARC Demo

This is an example of setting up [Actions Runner Controller](https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners-with-actions-runner-controller/about-actions-runner-controller) (ARC) on a Kubernetes cluster (Minikube in a Codespace).

This will create Actions runners in a GitHub organization.

## What's installed

- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [Docker](https://docs.docker.com/get-docker/)
- [Actions Runner Controller](https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners-with-actions-runner-controller/about-actions-runner-controller)

## How to use

- Use the `Use this template` button to create a new repository based on this repo. 
- Create a [personal access token](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token) with `admin:org, admin:org_hook, notifications, read:public_key, read:repo_hook, repo, workflow` scope
- Create a [Codespace secret](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces) named `ARC_DEMO_TOKEN` with the value of the personal access token created in the previous step
- Create another Codespace secret named `ARC_CONFIG_URL` with the value of the GitHub organization you want to create the runners in (e.g., `https://github.com/bxtp4p-demos`)
- Create a Codespace
- Make sure that Minikube is running by running `minikube start` in the terminal

## Using the runners in an Actions workflow

- Use `runs-on: arc-runner-set` in your workflow to target the runners created by ARC
