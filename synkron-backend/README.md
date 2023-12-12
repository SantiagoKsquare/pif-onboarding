# Setting up Synkron Backend

The first step is clone the repository [Synkron Backend](https://github.com/Ksquare-University/kportal-back) by ssh in your workspace.

Follow the instructions in [App Development](https://github.com/Ksquare-University/kportal-back#app-development) for the
sections bellow:

- Install dependencies running

```
npm run install
```

- Install git submodule (commons) running `git submodule`.

This command will install the subdmodule for https://github.com/KsquareTools/ksquare-ecosystem-commons

```
git submodule update --init --recursive
```

Now the backend repository is ready, please continue with the next topic.

NOTE: It is important to clone the repositories using ssh, because the command that installs the git submodule uses ssh and will fail if another method is used.

# Next Topic

[Connecting to the DB](../db-connection)

Sources:

- [Adding a new SSH key to your GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)
