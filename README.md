# Installation
> `npm install --save @types/passport-latest-windowsauth`

# Summary
This package contains type definitions for passport-latest-windowsauth (https://www.npmjs.com/package/passport-latest-windowsauth?activeTab=readme).

# Details
Files were exported from https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/passport-latest-windowsauth.
## [index.d.ts](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/passport-latest-windowsauth/index.d.ts)
````ts
// Type definitions for passport-latest-windowsauth 1.0.0
// Project: https://www.npmjs.com/package/passport-latest-windowsauth?activeTab=readme
// Definitions by: Emily Marigold Klassen <https://github.com/forivall>
// Definitions: https://github.com/DefinitelyTyped/DefinitelyTyped
// TypeScript Version: 2.3

import * as express from 'express';
import * as passport from 'passport';
import * as ldapjs from 'ldapjs';
import { TlsOptions } from 'tls';

declare namespace windowsauth {
    interface Options {
        ldap?: {
            url?: string | undefined
            maxConnections?: number | undefined
            base?: string | undefined
            bindDN?: string | undefined
            bindCredentials?: string | undefined
            tlsOptions?: TlsOptions | undefined;
            reconnect?: boolean | {
                initialDelay?: number | undefined,
                maxDelay?: number | undefined,
                failAfter?: number | undefined
            } | undefined;
            timeout?: number | undefined;
            connectTimeout?: number | undefined;
            idleTimeout?: number | undefined;
            binder?: ldapjs.Client | undefined
            client?: ldapjs.Client | undefined
        } | undefined;
        integrated?: boolean | undefined;
        getUserNameFromHeader?(req: express.Request): string;
        passReqToCallback?: boolean | undefined;
        usernameField?: string | undefined;
        passwordField?: string | undefined;
    }
    type Verified = (err: Error | undefined | null, user?: object, info?: object) => void;
    type Verify = (profile: passport.Profile, done: Verified) => void;
    type VerifyWithReq = (req: express.Request, profile: passport.Profile, done: Verified) => void;
}

declare class windowsauth extends passport.Strategy {
    constructor(options: windowsauth.Options & {passReqToCallback: true}, verify: windowsauth.VerifyWithReq);
    constructor(options: windowsauth.Options, verify: windowsauth.Verify);
    constructor(verify: windowsauth.Verify);
}

export = windowsauth;

````

### Additional Details
 * Last updated: Thu, 20 Jan 2023 
 * Dependencies: [@types/express](https://npmjs.com/package/@types/express), [@types/passport](https://npmjs.com/package/@types/passport), [@types/ldapjs](https://npmjs.com/package/@types/ldapjs)
 * Global values: none