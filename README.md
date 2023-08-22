# Cross-Platform Origin of Content (XPOC) Framework

This project introduces the Cross-Platform Origin of Content (XPOC) framework, along with a sample implementation.

The aim of the XPOC framework is to allow a person or organization (content owner) to create a authoritative list of
1. the various accounts they control over hosting web platforms (such as YouTube, X (formerly Twitter), Facebook, etc.), and
2. the various pieces of content (videos, posts, etc.) they created or approved on these platforms.

Using this framework, content creators protect themselves against falsely attributed accounts or content, providing signals that can be used by automated validation tools.

A content owner creates a XPOC manifest that contains references to the accounts they control and the content items they created across various platforms, and hosts it on its well-known website. The owner then adds a XPOC URI referencing its own manifest to their platform account pages (bio or profile) and content items. Verifiers can validate the origin of an account or content item using a XPOC URI by dereferencing it to retrieve the owner's manifest, and by verifying that the account or content item is listed within it. For details, see the framework's [specification](./doc//xpoc-specification.md).

The repository contains a sample implementation to create XPOC manifests and to verify XPOC content.

## System Overview

This section describes the life cycle for data protected using the Cross-Platform Origin of Content framework. The following diagram illustrates the [example](./doc/xpoc-specification.md#example) from the specification. (TODO: update diagram for account linking)

1. A content owner (Alex Example) creates a XPOC manifest on their website (`alexexample.com`) listing the content they've created across different platforms (e.g., a video on YouTube, a post on Facebook).
1. The content owner adds a XPOC URI (`xpoc://alexexample.com`) to each referenced content item (e.g., in the YouTube video description, in the Facebook post).
1. A verifier looking at the content item parses the XPOC URI, fetches the corresponding XPOC manifest, and verifies that the content item is indeed listed therein.  

![XPOC architecture](./doc/XPOC_arch.svg)

## Using the sample implementation

This section describes how to build and run the sample implementation.

### Setup

Make sure [node.js](https://nodejs.org/) and [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) are installed on your system; the latest Long-Term Support (LTS) version is recommended for both. 

Build the `npm` package:
```
npm install
npm run build
```

Start the server:
```
`npm run start-server`
```

By default, the server listens on port 3000; edit [server.ts](./src/server.ts) to modify this.


### Usage

The sample portal offers two pages: one to edit XPOC manifest, and one to verify XPOC-protected content.

* Manifest Editor: TODO: add more details after code refactoring
* XPOC validator: TODO: add more details after code refactoring

The XPOC validator supports different platforms, and its experience can be improved if the deployer enable API access to these platform; see [PLATFORM.md](./PLATFORM.md) for details. 

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
