# String Overflow (TypeScript)

[**⚖️** MIT](./LICENSE.md)

**🗂️**
[![GitHub: hugoalh-studio/string-overflow-ts](https://img.shields.io/badge/hugoalh--studio/string--overflow--ts-181717?logo=github&logoColor=ffffff&style=flat "GitHub: hugoalh-studio/string-overflow-ts")](https://github.com/hugoalh-studio/string-overflow-ts)
[![JSR: @hugoalh/string-overflow](https://img.shields.io/badge/JSR-@hugoalh/string--overflow-F7DF1E?labelColor=F7DF1E&logoColor=000000&style=flat "JSR: @hugoalh/string-overflow")](https://jsr.io/@hugoalh/string-overflow)

**🆙** ![Latest Release Version](https://img.shields.io/github/release/hugoalh-studio/string-overflow-ts?sort=semver&color=2187C0&label=&style=flat "Latest Release Version") (![Latest Release Date](https://img.shields.io/github/release-date/hugoalh-studio/string-overflow-ts?color=2187C0&label=&style=flat "Latest Release Date"))

A TypeScript module to truncate the string with the specify length; Safe with the emojis, URLs, and words.

## 🎯 Target

- Bun ^ v1.0.0
- Cloudflare Workers
- Deno >= v1.34.0 / >= v1.41.1 *(Via JSR)*
  > **🛡️ Require Permission**
  >
  > *N/A*
- NodeJS >= v20.9.0

### 🔗 Other Edition

- [JavaScript](https://github.com/hugoalh-studio/string-overflow-js)

## 🔰 Usage

### Via HTTPS

> **🎯 Supported Target**
>
> - Deno

1. Import at the script (`<ScriptName>.ts`):
    - Via DenoPKG
      ```ts
      import ... from "https://denopkg.com/hugoalh-studio/string-overflow-ts[@<Tag>]/mod.ts";
      ```
    - Via GitHub Raw (Require Tag)
      ```ts
      import ... from "https://raw.githubusercontent.com/hugoalh-studio/string-overflow-ts/<Tag>/mod.ts";
      ```
    - Via Pax
      ```ts
      import ... from "https://pax.deno.dev/hugoalh-studio/string-overflow-ts[@<Tag>]/mod.ts";
      ```
    > **ℹ️ Note**
    >
    > Although it is recommended to import the entire module with the main path `mod.ts`, it is also able to import part of the module with sub path if available, but do not import if:
    >
    > - it's file path has an underscore prefix (e.g.: `_foo.ts`, `_util/bar.ts`), or
    > - it is a benchmark or test file (e.g.: `foo.bench.ts`, `foo.test.ts`), or
    > - it's symbol has an underscore prefix (e.g.: `export function _baz() {}`).
    >
    > These elements are not considered part of the public API, thus no stability is guaranteed for them.

### Via JSR With Native Support

> **🎯 Supported Target**
>
> - Deno

1. Import at the script (`<ScriptName>.ts`):
    ```ts
    import ... from "jsr:@hugoalh/string-overflow[@<Tag>]";
    ```
    > **ℹ️ Note**
    >
    > Although it is recommended to import the entire module, it is also able to import part of the module with sub path if available, please visit [file `jsr.jsonc`](./jsr.jsonc) property `exports` for available sub paths.

### Via JSR With NPM Compatibility Layer Support

> **🎯 Supported Target**
>
> - Bun
> - Cloudflare Workers
> - NodeJS

1. Install via console/shell/terminal:
    - Via Bun
      ```sh
      bunx jsr add @hugoalh/string-overflow[@<Tag>]
      ```
    - Via NPM
      ```sh
      npx jsr add @hugoalh/string-overflow[@<Tag>]
      ```
    - Via PNPM
      ```sh
      pnpm dlx jsr add @hugoalh/string-overflow[@<Tag>]
      ```
    - Via Yarn
      ```sh
      yarn dlx jsr add @hugoalh/string-overflow[@<Tag>]
      ```
2. Import at the script (`<ScriptName>.ts`):
    ```ts
    import ... from "@hugoalh/string-overflow";
    ```
    > **ℹ️ Note**
    >
    > Although it is recommended to import the entire module, it is also able to import part of the module with sub path if available, please visit [file `jsr.jsonc`](./jsr.jsonc) property `exports` for available sub paths.

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
  new StringOverflow(100).truncate(text);
  truncateString(text, 100);
  //=> "Vel ex sit est sit est tempor enim et voluptua consetetur gubergren gubergren ut. Amet dolores ..."

  /* Either */
  new StringOverflow(100, { safeWords: false }).truncate(text);
  truncateString(text, 100, { safeWords: false });
  //=> "Vel ex sit est sit est tempor enim et voluptua consetetur gubergren gubergren ut. Amet dolores si..."
  ```
