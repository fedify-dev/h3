@fedify/h3: Integrate Fedify with h3
====================================

> [!IMPORTANT]
> This repository is obsolete and has been archived in favor of the monorepo
> [fedify-dev/fedify].

[![npm][npm badge]][npm]
[![Matrix][Matrix badge]][Matrix]
[![Follow @fedify@hollo.social][@fedify@hollo.social badge]][@fedify@hollo.social]

This package provides a simple way to integrate [Fedify] with [h3],
an HTTP server framework behind [Nitro], [Analog], [Vinxi],
[SolidStart], [TanStack Start], and other many web frameworks.

The integration code looks like this:

~~~~ typescript
import { createApp, createRouter } from "h3";
import { integrateFederation, onError } from "@fedify/h3";
import { federation } from "./federation";  // Your `Federation` instance

export const app = createApp({ onError });
app.use(
  integrateFederation(
    federation,
    (event, request) => "context data goes here"
  )
);

const router = createRouter();
app.use(router);
~~~~

> [!NOTE]
> Your app has to configure `onError` to let Fedify negotiate content types.
> If you don't do this, Fedify will not be able to respond with a proper error
> status code when a content negotiation fails.

[fedify-dev/fedify]: https://github.com/fedify-dev/fedify
[npm]: https://www.npmjs.com/package/@fedify/h3
[npm badge]: https://img.shields.io/npm/v/@fedify/h3?logo=npm
[Matrix]: https://matrix.to/#/#fedify:matrix.org
[Matrix badge]: https://img.shields.io/matrix/fedify%3Amatrix.org
[@fedify@hollo.social badge]: https://fedi-badge.deno.dev/@fedify@hollo.social/followers.svg
[@fedify@hollo.social]: https://hollo.social/@fedify
[Fedify]: https://fedify.dev/
[h3]: https://h3.unjs.io/
[Nitro]: https://nitro.unjs.io/
[Analog]: https://analogjs.org/
[Vinxi]: https://vinxi.vercel.app/
[SolidStart]: https://start.solidjs.com/
[TanStack Start]: https://tanstack.com/start


Changelog
---------

### Version 0.1.3

To be released.

### Version 0.1.2

Released on February 28, 2025.

 -  Made the package compatible with Fedify 1.0.0 or later.

### Version 0.1.1

Released on August 6, 2024.

 -  Added missing entry points to the *package.json*.

### Version 0.1.0

Initial release.  Released on July 6, 2024.
