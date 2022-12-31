# Contributions Guidelines

## Forking
When forking this project, please use a personal fork, rather than an organization fork.

We may routinely modify your pull request, whether it's a quick rebase or to take care of any minor nitpicks we might have. Often, it's better for us to solve these problems for you than make you go back and forth trying to fix it yourself.

Unfortunately, if you use an organization for your pull request, or disallow fork modification, it prevents us from modifying it. This requires us to manually merge your pull request, resulting in its closure instead of being marked as merged.

We much prefer to have pull requests show as merged, so please do not use repositories on organizations for pull reqeusts.

See <https://github.com/isaacs/github/issues/1681> for more information on the issue.

## Code formatting
Try to follow the existing formatting. Style guidelines are typically stored inside the `.eslintrc.json` file.

In general, in order of importance:

- Prefer readability over dogma.
- Keep to the existing formatting.
- Indent with 4 space unless it's in a submodule.
- Use double quotes (`"`) instead of single quotes (`'`).
- Make sure your IDE is not messing up line endings or whitespace.
- Document your changes.

### Examples
#### ![TypeScript](typescript.svg)
```ts
/**
 * Properties for the {@link helloWorld} function.
 */
interface helloWorldProps {
    /**
     * Whether to print to the console.
     */
    "print"?: boolean,
    
    /**
     * Contents of the array to print.
     */
    "array"?: string[]
}

/**
 * Whether the program has run the {@link helloWorld} function.
 *
 * @see helloWorld
 */
let didHello = false;

/**
 * Prints "Hello World!" and the contents of an array.
 * 
 * @remarks
 * Not very useful.
 */
function helloWorld({ print = true, array = [] }: helloWorldProps) {
    if (print) {
        console.log("Hello World!");
        
        // This only exists to demonstrate my template literal style
        console.log(`Here's an array: ${array.join(", ")}`);
    }
    
    didHello = true;
}

// Print helloWorld
helloWorld({
    "print": true,
    "array": ["hello", "world"]
});
```

#### ![Java](java.svg)
```java
// W.I.P.
```

## Signing your work
In an effort to ensure that the code you contribute is actually compatible with the licenses in this codebase, we request for you to sign-off all your contributions.

This can be done by appending `-s` to your `git commit` call, or by manually appending the following text to your commit message:

```
<commit message>

Signed-off-by: Author name <Author email>
```

By signing off your work, you agree to the terms below:

```
Developer's Certificate of Origin 1.1

By making a contribution to this project, I certify that:

(a) The contribution was created in whole or in part by me and I
    have the right to submit it under the open source license
    indicated in the file; or

(b) The contribution is based upon previous work that, to the best
    of my knowledge, is covered under an appropriate open source
    license and I have the right under that license to submit that
    work with modifications, whether created in whole or in part
    by me, under the same open source license (unless I am
    permitted to submit under a different license), as indicated
    in the file; or

(c) The contribution was provided directly to me by some other
    person who certified (a), (b) or (c) and I have not modified
    it.

(d) I understand and agree that this project and the contribution
    are public and that a record of the contribution (including all
    personal information I submit with it, including my sign-off) is
    maintained indefinitely and may be redistributed consistent with
    this project or the open source license(s) involved.
```

These terms will be enforced once you create a pull request, and you will be informed if any of your commits aren't signed-off by you.

As a bonus, you can also [cryptographically sign your commits][gh-signing-commits] and enable [vigilant mode][gh-vigilant-mode] on GitHub.

## Attribution
This Contributing document is adapted from [PrismLauncher's Contributing document][prism].

Icons are provided from [Simple Icons](simple-icons).

[gh-signing-commits]: https://docs.github.com/en/authentication/managing-commit-signature-verification/signing-commits
[gh-vigilant-mode]: https://docs.github.com/en/authentication/managing-commit-signature-verification/displaying-verification-statuses-for-all-of-your-commits
[prism]: https://github.com/PrismLauncher/PrismLauncher/blob/4b12c85d91be34504384117584fb4f25a754481e/CONTRIBUTING.md
[simple-icons]: https://simpleicons.org
