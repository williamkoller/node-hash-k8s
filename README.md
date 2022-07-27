<h1 align="center">Node Hash Kubernetes</h1>

<p align="justify">Example the app Nodejs with Docker, Kind and K8S</p>

- Required installed `docker`, `yarn`, `nodejs`, `kind`, and `kubernetes`

- Add in your `.zshrc` in line `alias k="kubectl"` and `source ~/.zshrc`

<h3>Steps to run the project</h3>

1 - install dependencies
  - `yarn install`

2 - running image docker
  - `docker build -t node-hash .`

3 - create cluster with kind
  - `kind create cluster`

4 - load docker-image in kind
  - `kind load docker-image node-hash`

5 - kubernetes apply 
  - `k apply -f kubernetes/manifest.yaml`

6 - verify deploy
  - `k get deploy`

7 - how access app
  - `k port-forward service/node-hash 3008:80`
  - response:
  ```
  k port-forward service/node-hash 3008:80
  Forwarding from 127.0.0.1:3008 -> 8080
  Forwarding from [::1]:3008 -> 8080
  ```

Made with 🖤 by [williamkoller](https://github.com/williamkoller) :wave:
