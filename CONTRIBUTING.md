# Contributing to ManoMano Organization

Common guidelines for contributing to ManoMano projects

## Foreword

First off, thank you for taking the time to contribute! 

It's worth mentioning that the purpose of this document is to provide you with a set of general guidelines and not
strict rules: nothing is set in stone and we welcome contributions about these contributing guidelines as well :-)

## TL;DR

We want to make contributing straightforward and easy for everyone. As such and unless otherwise stated, we will use the
traditional GitHub fork and pull workflow: any commit must be made to a feature/topic branch in a local fork and
submitted via a pull request before it can be merged. If you are familiar with GitHub (and Git), branching and opening a
pull request or an issue... then you should be able to start contributing right away. 

It is **strongly advised** to contact the project owner(s) **before** working on implementing a new feature or making
any kind of large code refactoring.

Contributors must agree to the following:

- material without explicit copyright assignment will be assigned to [ManoMano](https://manomano.fr)
- apart from a few identified exceptions, material must be licensed under the [ISC
license](https://opensource.org/licenses/isc-license.txt); in all cases, a **license is mandatory**.

ManoMano staff should also be aware of [additional guidelines](#additional-guidelines-for-manomano-staff).

## Coding style

Follow the project's conventions.

We usually do not want to enforce a particular style because we intend to host a lot of different projects by a lot of
people with different backgrounds. That said, we do request style **consistency within the same project**, this is
especially important for reusable projects (module or librairies) that will have more scrutiny.

Contact the contributors if you new help with tooling.

## Documentation

We consider documentation as important as code. Substantial contribution must always come with exhaustive documentation. 

## Tests

Application and contributions should be tested and push for the highest quality standard. 

Maintainers could help you writing tests and with the tooling.

## Git

Make sure you have a [GitHub account](https://github.com/join).
The *main* branch should be considered as the production/deploy branch.

### Workflow

Extensive information can be found in this excellent [forking workflow
tutorial](https://www.atlassian.com/git/tutorials/comparing-workflows#forking-workflow).

In a nutshell:

1. [Fork](https://help.github.com/articles/fork-a-repo) the repository and clone it locally.  

    ```
    git clone https://github.com/${USERNAME}/${REPONAME}
    cd ${REPONAME}
    ```

2. Create a topic branch where changes will be done.

    ```
    git checkout -b ${TOPIC_BRANCH}
    ```

3. Commit the changes in logical and incremental chunks and use [interactive
rebase](https://help.github.com/articles/about-git-rebase) when needed. 

    In your [commit message](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html), make sure to:

    - use the present tense
    - use the imperative mood
    - limit the first line to 72 characters
    - reference any associated issues and/or PRs (if applicable)

    ```
    git commit -am 'Add new feature...'
    ```

4. Push the topic branch to the remote forked repository.

    ```
    git push origin ${TOPIC_BRANCH}
    ```

5. Open a [Pull request](https://help.github.com/articles/about-pull-requests) to the upstream repository with a clear
title and description.

6. Once the PR has been merged, the topic branch can be removed from the local fork.

    ```
    git branch -d ${TOPIC_BRANCH}
    git push origin --delete ${TOPIC_BRANCH}
    ```

### Syncing a fork with its upstream

This is used to keep a local fork up-to-date with the original upstream repository.

1. Connect the local to the original upstream repository.

    ```
    git remote add upstream https://github.com/${USERNAME}/${REPONAME}
    ```

2. Checkout, fetch and merge the upstream master branch to the local one.

    ```
    git checkout main
    git fetch upstream
    git merge upstream/master
    ```

3. Push changes to update to remote forked repository.

    ```
    git push
    ```

See [GitHub help](https://help.github.com/articles/syncing-a-fork) for more information.

## Issues

If you find a bug that you don't know how to fix, please create an [issue](https://guides.github.com/features/issues/):

- use a clear and descriptive title
- give a step by step explanation on how to reproduce the problem
- include as many details as possible, even ones that may seem irrelevant; [gists](https://help.github.com/articles/about-gists/) are a good way to include large amount of context and information
- describe what was already tried to fix the problem

## Additional guidelines for ManoMano staff

Anyone from ManoMano staff willing to setup a new project can ask one of the organisation owners to create a repository
which (s)he will be the owner and responsible of the contributing workflow like answering issues, reviewing and merging
pull requests, etc.

### The ManoManoTech core team

By default, members of the core team watch and have admin rights over all projects and hence can handle the global
contributions workflow.

### Organization members

There won't be any organization members besides the owners and members of the core team and the default configuration
(right etc.) will not be modified.

That also means that if a user leaves the core team, (s)he must be removed from the organization members list (i.e. orga
members and core team members must stay in sync).

### Organization owners

Organization owners have full control over the ManoManoTech organization and are the only one with repository creation
rights.

They can also dismiss the requirement of opening a pull request to commit something but that is only done on rare
exceptions.

#### Creating a new repository

Note that status checks (Travis etc.) are not a requirement.

1. Go to the top level URL of the [ManoManoTech organization](https://github.com/ManoManoTech)

2. Click on [**New**] then:

    - Make sure the **Owner** is set to ManoManoTech
    - Give it a meaningful [Repository name](#naming-conventions) and
    **Description**
    - Check the **Initialize** this repository with a README box and click on [**Create repository**]

3. Click on **Add topics** and add a few descriptive tags then click on [**Done**].

4. Go to **Settings** and uncheck the **Wikis** box

5. Go to the **Collaborators & teams** tab then:

    - Add **core** to the **Teams** list and give it **Admin** access
    - Add the project submitter username to the **Collaborators** list and give him/her **Admin** access (even if the
    submitter is already a member/owner of the ManoManoTech organization or the core team because (s)he may leave the
    orga at some point)

6. Go to the **Branches** tab and select **main** under the **Protected branches** section

7. Check **Protect this branch** then [**Save changes**]

8. Add the default [LICENSE](LICENSE) and [CONTRIBUTING.md](CONTRIBUTING.md) files to the repository

##### Naming conventions

There are multiple types of repositories.

| Type                           | Convention            | Example                 |
|--------------------------------|-----------------------|-------------------------|
| wrapped up solution (use case) | demo-vendor-tech-name | demo-aws-lambda-foobar  |
| generic reusable recipes       | tech-type             | ansible-roles           |
| software                       | software name         | superduperutility       |
| organizational repo            | self-explanatory      | contributing-guidelines |
| forked repositories            | none                  | terraform               |

#### Forking an upstream repository

1. [Fork](Fork) the repository

2. Uncheck the **Wikis** box

3. Go to the **Collaborators & teams** tab then:

    - Add **core** to the **Teams** list and give it **Admin** access
    - Make sure the **Collaborators** list is empty

Regularly keep the forked repository up-to-date with its upstream: see Syncing a fork with its upstream for details.

Please refer to our [contributing guidelines](https://github.com/ManoManoTech/ALaMano).
