# Security policy

The Mizwala app downloads the files in this repository's releases only when a reader asks for them, and checks each
one against the SHA-256 listed in the [README](README.md) before installing it. The main risk here is a file that
has been replaced or tampered with.

## Reporting a problem

Please report it **privately**. Do not open a public issue or pull request.

Use GitHub private vulnerability reporting: open the repository's **Security** tab, choose **Report a
vulnerability** (https://github.com/Ahmad-AlModhayan/mizwala-content/security/advisories/new). If you cannot use
GitHub, write to hello@kahflabs.com with "security" in the subject.

Include which file or release, what you found, and how to reproduce it.

## In scope

- A release file whose SHA-256 does not match the one in the README.
- A way to replace or alter a release file without the repository owner's action.
- Content that makes the app misbehave when it loads the file.

## Rights holders

This is not a security matter. If you hold the rights to a text redistributed here and want it removed, open a
public issue or write to hello@kahflabs.com, as the README says; it will be taken down.

## What to expect

You get an answer within two weeks. A confirmed problem is fixed before anything is said in public, and you are
credited in the advisory unless you would rather not be.
