# Prisma 2 Github Actions bug

Simple reproduction of a bug when trying to run `prisma2 generate` as apart of a workflow in github actions.

### Setup

This project is created via `npx prisma2 init`. The options selected were:

```
Starter Project
Javascript
GraphQL + Auth
SQLite
```

### Bug
Currently the action is set up to run on pushing commits. See [the workflow file](https://github.com/iRoachie/prisma2-github-ci/blob/master/.github/workflows/blank.yml) for the actions run.

I've pasted the error here, but you can also view the ci https://github.com/iRoachie/prisma2-github-ci/commit/129fdff7e6c04349427d84778dc12527d9e2d4e8/checks?check_suite_id=300148988#step:4:17.

```bash
$ npm -s run generate
18
Error: Error: Command failed with exit code 2 (ENOENT): /github/workspace/node_modules/prisma2/query-engine-linux-glibc-libssl1.1.0 cli --dmmf
19
spawn /github/workspace/node_modules/prisma2/query-engine-linux-glibc-libssl1.1.0 ENOENT
20
error Command failed with exit code 1.
21
info Visit https://yarnpkg.com/en/docs/cli/install for documentation about this command.
22
##[error]Docker run failed with exit code 1
```


