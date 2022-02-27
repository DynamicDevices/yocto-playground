# yocto-playground

This is a sandbox to test cloud building of Yocto recipes and images.

I've wanted to have some simple CI building going for Yocto for quite some time but have never managed to find a cloud builder that would build for long enough. I used Jenkins for some years but I recently discovered that GitHub allows self-hosted builders. This means that when a trigger occurs, such as a push to a repository or a pull request, a GitHub workflow can be kicked off to run on my own build systems. This is ideal for Yocto.

An example workflow is defined [here](https://github.com/DynamicDevices/yocto-playground/blob/main/.github/workflows/CI_github.yml) and you can see that we

- define branches and target architectures we're building against
- check out or update Yocto Poky and some supporting layers
- actually build an image
- run some testing on the image
- upload the build artifacts (which can then be accessed through the GitHub UI)

You can see the example runs [here](https://github.com/DynamicDevices/yocto-playground/actions)

And the current workflow status is ![workflow image](https://img.shields.io/github/workflow/status/dynamicdevices/yocto-playground/Build%20Yocto%20Image)

# Setup

If you want to configure a self-hosted runner on your account see background [here](https://docs.github.com/en/actions/hosting-your-own-runners/about-self-hosted-runners).

I have the DynamicDevices organisation and I have self-hosted runners configured on there which I then allow to run on certain repositories
