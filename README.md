# Deploy gh-pages github

```yml
name: Build and Deploy
on:
  push:
    branches:
      - main
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: All things angular
      uses: AhsanAyaz/angular-deploy-gh-pages-actions@v1.3.2 ## replace by latest version without it you will see Expected format {org}/{repo}[/path]@ref. Actual 'AhsanAyaz/angular-deploy-gh-pages-actions',Input string was not in a correct format.
      with:
        github_access_token: ${{ secrets.ACCESS_TOKEN }} # see the Configuration section for how you can create secrets
        build_configuration: production # The build environment for the app. please look configurations in your angular.json
        base_href: /angular-deploy-github/   # make sure this corresponds to https://<your_username>.github.io/<base_href>/
        deploy_branch: gh-pages # The branch the action should deploy to.
        angular_dist_build_folder: dist/angular-deploy-github # The folder where your project is supposed to be after running ng build by the action.
```

https://id1945.github.io/angular-deploy-github
