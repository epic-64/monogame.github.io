# monogame.github.io

This repository contains the documentation and the website for MonoGame.

## Building Form Source
The MonoGame website is built using the .NET tool [DocFX](https://dotnet.github.io/docfx/) to generate the API reference documentation and the static site generator [11ty](https://www.11ty.dev/) to generate the full website.  This means you will need the following prerequisites to build locally from source

1. .NET SDK version 6.0 or higher installed ([download](https://dotnet.microsoft.com/en-us/download))
2. Node.js and NPM installed ([download](https://nodejs.org/en))

With your environment setup properly, the following explains how to build from source

1. Clone this repository

```sh
git clone https://github.com/MonoGame/monogame.github.io.git
```

2. Install npm dependencies

```sh
npm install
```

3. Optional Steps
   1. If you want to generate the API Reference documentation locally, you will need to ensure that the MonoGame submodule has been initialized by running `git submodule update --init --recursive`
4. Run a local build and serve it with hot reloading.  Depending on what part of the site you are working on, there are different commands you can use. They are explained in the table below

| Command | Generates Website | Generates Articles | Generates API | Description |
| --- | --- | --- | --- | --- |
| `npm run dev` | ✔ | ✔ | ✔ | This will run and serve the full website, including the web pages generated by 11ty and the articles and api documentation built by docfx.  This can be slower to use when developing since all API documentation (~500 files) will be built initially and again during each hot reload change.  If you're not working specifically on the API documentation page, it is suggested to use one of the other commands instead. |
| `npm run website` | ✔ | ❌ | ❌ | This will run and serve the website with only the web pages genereated by 11ty.  The articles and api documentation generated by docfx will be bypassed.  This is useful when you're only working on the main website pages and want fast hot reloading.|
| `npm run articles` | ✔ | ✔ | ❌ | This will run and serve the website including the webpages generated by 11ty and the articles genereated by docfx only.  It will not generate the API documentation.  This is to allow fast hot reloading while working on the articles by not having all API documentation files (~500 files) be included. |
| `npm run build` | ✔ | ✔ | ✔ | This will perform a full build of the website, including the web pages built in 11ty and the articles and api documentation built by docfx. |

## LICENSE

The MonoGame project is under the Microsoft Public License except for a few portions of the code. See the [LICENSE](LICENSE) file for more details.
