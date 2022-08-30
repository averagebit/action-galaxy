# action-galaxy (Github Action)

## Description

The action will publish the Ansible role in the repository to Ansible
Galaxy.

## Requirements

The action uses the `ansible-galaxy role import` tool/command so it
expects the [common](https://galaxy.ansible.com/docs/contributing/creating_role.html) Ansible role directory structure.

## Inputs

- `galaxy_token`
  - Description: The account holders Ansible Galaxy access token. Found
    at Profile > Preferences > API Key.

## Usage

```yml
name: publish

on:
  - push

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: checkout
        uses: actions/checkout@v2
      - name: galaxy
        uses: averagebit/action-galaxy@1.0.0
        with:
          galaxy_token: ${{ secrets.galaxy_token }}
```

## Legal

Copyright 2022 averagebit <[averagebit@pm.me](mailto:averagebit@pm.me)>

Licensed under the Apache License, Version 2.0 (the "License"); you may
not use this file except in compliance with the License. You may obtain
a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
