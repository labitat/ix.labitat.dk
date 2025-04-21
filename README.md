# LabIX

Website files for [ix.labitat.dk](https://ix.labitat.dk/).

It is build using the static site generator [Hugo](https://gohugo.io/) and uses the [Paige](https://github.com/willfaught/paige) theme.


## Setup
Much inspiration from [Paige docs](https://github.com/willfaught/paige/blob/master/README.md):

1. [Install Hugo](https://gohugo.io/installation/) (the extended version, and at least 0.111.3).

    For Homebrew on Mac:

    ```sh
    $ brew install hugo
    ```

    For Chocolatey on Windows:

    ```sh
    $ choco install hugo-extended
    ```

    For Snap on Linux:

    ```sh
    $ sudo snap install hugo
    ```
    For Arch: 

    ```sh
    pamac build hugo-exteneded-cli
    ```

2. [Install Embedded Dart Sass](https://github.com/sass/dart-sass-embedded/releases).

    For Homebrew on Mac:

    ```sh
    $ brew install sass/sass/dart-sass-embedded
    ```

    For Chocolatey on Windows:

    ```sh
    $ choco install dart-sass-embedded
    ```

    For Snap on Linux:

    ```sh
    $ sudo snap install dart-sass-embedded
    ```

    For Arch:

    ```sh
    pamac build dart-sass-embedded
    ```

3. Build and run the site:
    ```sh
    $ cd ix.labiat.dk
    $ hugo server -D
    ```

    The argument `-D` includes content marked as a draft

## Publish site

Build files
```sh
hugo
```

Files can be found in the `public/` directory, it does not include any [draft, future or expired content](https://gohugo.io/getting-started/usage/#draft-future-and-expired-content).


Note that CI/CD deployment has not been set up yet.
