# Onboarding Codelab Node.js

Howdy! Glad to see you here partner 🤠
Welcome the ranch

## How do I get started?

1. Clone this repository
```shell
git clone https://github.com/wisemen-digital/onboarding-codelab-backend.git
```

2. Open the cloned repo

```shell
cd onboarding-codelab-backend
```

3. Verfiy your installation of node and install Node if you don't have it already
```shell
node -v 
brew install node
```

4. Install the npm dependencies
```shell
pnpm install
```

5. **Apple Silicon Mac users only:** Install Rosetta 2 if you haven't already
   
   CLAAT (the codelab tool) only provides Intel binaries, so Apple Silicon Macs need Rosetta 2 to run them.
   ```shell
   softwareupdate --install-rosetta --agree-to-license
   ```
   
   If you skip this step, you'll see an error like `Bad CPU type in executable` when running the server.

6. Start the local server to start the codelab
```shell
pnpm docs:serve
```

7. Open the [codelab](http://127.0.0.1:8080) in your browser to get started
8. Profit 😎


## Got any questions or suggestions?

Don't hesitate to contact your buddy or other members of our tech stack. 
We're always happy to help and open to improve our onboarding experience 💪.
Wisemen to the moon 🚀
