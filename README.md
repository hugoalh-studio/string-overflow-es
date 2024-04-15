# String Overflow (ES)

[**⚖️** MIT](./LICENSE.md)

[![GitHub: hugoalh-studio/string-overflow-es](https://img.shields.io/github/v/release/hugoalh-studio/string-overflow-es?label=hugoalh-studio/string-overflow-es&labelColor=181717&logo=github&logoColor=ffffff&sort=semver&style=flat "GitHub: hugoalh-studio/string-overflow-es")](https://github.com/hugoalh-studio/string-overflow-es)
[![JSR: @hugoalh/string-overflow](https://img.shields.io/jsr/v/@hugoalh/string-overflow?label=JSR%20@hugoalh/string-overflow&labelColor=F7DF1E&logoColor=000000&style=flat "JSR: @hugoalh/string-overflow")](https://jsr.io/@hugoalh/string-overflow)
[![NPM: @hugoalh/string-overflow](https://img.shields.io/npm/v/@hugoalh/string-overflow?label=@hugoalh/string-overflow&labelColor=CB3837&logo=npm&logoColor=ffffff&style=flat "NPM: @hugoalh/string-overflow")](https://www.npmjs.com/package/@hugoalh/string-overflow)

An ES (JavaScript & TypeScript) module to truncate the string with the specify length; Safe with the emojis, URLs, and words.

## 🎯 Target

- Bun ^ v1.0.0
- Cloudflare Workers
- Deno >= v1.34.0 / >= v1.41.1 (For JSR Only)
  > **🛡️ Require Permission**
  >
  > *N/A*
- NodeJS >= v20.9.0

## 🔰 Usage

### Via JSR With `node_modules`

> **🎯 Supported Target**
>
> - Bun
> - Cloudflare Workers
> - NodeJS

1. Install via:
    - Bun
      ```sh
      bunx jsr add @hugoalh/string-overflow[@${Tag}]
      ```
    - NPM
      ```sh
      npx jsr add @hugoalh/string-overflow[@${Tag}]
      ```
    - PNPM
      ```sh
      pnpm dlx jsr add @hugoalh/string-overflow[@${Tag}]
      ```
    - Yarn
      ```sh
      yarn dlx jsr add @hugoalh/string-overflow[@${Tag}]
      ```
2. Import at the script:
    ```ts
    import ... from "@hugoalh/string-overflow";
    ```

> **ℹ️ Note**
>
> - Although it is recommended to import the entire module, it is also able to import part of the module with sub path if available, please visit [file `jsr.jsonc`](./jsr.jsonc) property `exports` for available sub paths.
> - It is recommended to import the module with tag for immutability.

### Via JSR With Specifier

> **🎯 Supported Target**
>
> - Deno

1. Import at the script:
    ```ts
    import ... from "jsr:@hugoalh/string-overflow[@${Tag}]";
    ```

> **ℹ️ Note**
>
> - Although it is recommended to import the entire module, it is also able to import part of the module with sub path if available, please visit [file `jsr.jsonc`](./jsr.jsonc) property `exports` for available sub paths.
> - It is recommended to import the module with tag for immutability.

### Via NPM With `node_modules`

> **🎯 Supported Target**
>
> - Cloudflare Workers
> - NodeJS

1. Install via:
    - NPM
      ```sh
      npm install @hugoalh/string-overflow[@${Tag}]
      ```
    - PNPM
      ```sh
      pnpm add @hugoalh/string-overflow[@${Tag}]
      ```
    - Yarn
      ```sh
      yarn add @hugoalh/string-overflow[@${Tag}]
      ```
2. Import at the script:
    ```ts
    import ... from "@hugoalh/string-overflow";
    ```

> **ℹ️ Note**
>
> - Although it is recommended to import the entire module, it is also able to import part of the module with sub path if available, please visit [file `jsr.jsonc`](./jsr.jsonc) property `exports` for available sub paths.
> - It is recommended to import the module with tag for immutability.

### Via NPM With Specifier

> **🎯 Supported Target**
>
> - Bun
> - Deno

1. Import at the script:
    ```ts
    import ... from "npm:@hugoalh/string-overflow[@${Tag}]";
    ```

> **ℹ️ Note**
>
> - Although it is recommended to import the entire module, it is also able to import part of the module with sub path if available, please visit [file `jsr.jsonc`](./jsr.jsonc) property `exports` for available sub paths.
> - It is recommended to import the module with tag for immutability.

### Via Remote Import

> **🎯 Supported Target**
>
> - Deno

1. Import at the script:
    ```ts
    /* Via GitHub Raw (Require Tag) */
    import ... from "https://raw.githubusercontent.com/hugoalh-studio/string-overflow-es/${Tag}/mod.ts";
    ```

> **ℹ️ Note**
>
> - Although it is recommended to import the entire module with the main path `mod.ts`, it is also able to import part of the module with sub path if available, but do not import if:
>
>   - it's file path has an underscore prefix (e.g.: `_foo.ts`, `_util/bar.ts`), or
>   - it is a benchmark or test file (e.g.: `foo.bench.ts`, `foo.test.ts`), or
>   - it's symbol has an underscore prefix (e.g.: `export function _baz() {}`).
>
>   These elements are not considered part of the public API, thus no stability is guaranteed for them.
> - Although there have 3rd party services which provide enhanced, equal, or similar methods/ways to remote import the module, beware these services maybe inject unrelated elements and thus affect the security.

## 🧩 API

- ```ts
  class StringTruncator {
    constructor(maximumLength: number, options: StringTruncatorOptions = {}): StringTruncator;
    truncate(item: string, maximumLengthOverride?: number): string;
    static truncate(item: string, maximumLength: number, options: StringTruncatorOptions = {}): string;
  }
  ```
- ```ts
  function truncateString(item: string, maximumLength: number, options: StringTruncatorOptions = {}): string;
  ```
- ```ts
  enum StringTruncateEllipsisPosition {
    end = "end",
    End = "end",
    middle = "middle",
    Middle = "middle",
    start = "start",
    Start = "start"
  }
  ```
- ```ts
  interface StringTruncatorOptions extends StringDissectorOptions {
    /**
    * Ellipsis mark of the target string.
    * @default "..."
    */
    ellipsisMark?: string;
    /**
    * Ellipsis position at the target string.
    * @default "end"
    */
    ellipsisPosition?: StringTruncateEllipsisPosition | keyof typeof StringTruncateEllipsisPosition;
  }
  ```

> **ℹ️ Note**
>
> For the prettier documentation, can visit via:
>
> - [Deno CLI `deno doc`](https://deno.land/manual/tools/documentation_generator)
> - [JSR](https://jsr.io/@hugoalh/string-overflow)

## ✍️ Example

- ```ts
  const text = "Vel ex sit est sit est tempor enim et voluptua consetetur gubergren gubergren ut. Amet dolores sit. Duo iriure vel dolore illum diam. Ea vero diam diam tincidunt molestie elitr te sed nisl ut vulputate tincidunt accusam sit sed. Amet sea dolore rebum amet accusam labore dolor no sadipscing labore. Sit erat sit sed voluptua tempor sit ea dolor et.";

  /* Either */
  new StringTruncator(100).truncate(text);
  truncateString(text, 100);
  //=> "Vel ex sit est sit est tempor enim et voluptua consetetur gubergren gubergren ut. Amet dolores ..."

  /* Either */
  new StringTruncator(100, { safeWords: false }).truncate(text);
  truncateString(text, 100, { safeWords: false });
  //=> "Vel ex sit est sit est tempor enim et voluptua consetetur gubergren gubergren ut. Amet dolores si..."
  ```
