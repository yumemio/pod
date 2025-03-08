# `pod` - barebones podcast management script

A minimal set of tools to manage podcast channels. Written in bash and Python.

![](demo.gif)

## Prerequisites

- Bash
- Python 3

## Installation

Create a directory for podcasts and deploy the scripts:

```
$ git clone https://github.com/yumemio/pod
$ mv pod ~/rec/podcasts
$ cd ~/rec/podcasts
```

Install the required dependencies:

```console
$ pip install -r requirements.txt
```

Give necessary permissions:

```console
$ chmod -R u+x ./pod ./bin
```

## Usage

### 1. Create a Podcast Channel

```console
$ ./pod create <title> <url>
```

- **title**: The name you assign to this podcast channel (used as a directory name)
- **url**: The podcast feed URL

Initializes a directory `<title>` and saves the podcast URL in `_url`.

#### Example

```console
$ ./pod create me-myself-ai https://feeds.megaphone.fm/TPG7603691495
```

### 2. List Episodes of a Podcast Channel

```console
$ ./pod list <title>
```

- **title**: The name of the podcast channel.
- Lists available episodes.

#### Example

```console
$ ./pod list me-myself-ai
```

Lists episodes from `me-myself-ai`.

### 3. Download Podcast Episodes

```console
$ ./pod download <title> <id|id1,id2|id1-id3>
```

- **title**: The name of the podcast channel
- **id|id1,id2|id1-id3**: Specifies which episodes to download. Use the IDs
  shown in the output of `./pod list`.
- Downloads the episodes to the `<title>/` directory.

#### Example

```console
$ ./pod download me-myself-ai 1
```

Downloads the latest episode of `me-myself-ai`.

```console
$ ./pod download me-myself-ai 3,5,7
```

Downloads episodes `3`, `5`, and `7`.

```console
$ ./pod download me-myself-ai 1-5
```

Downloads episodes `1` through `5`.

Use your favorite media player to listen to the downloaded episodes.

## Notes

- This Git repository is configured to ignore everything except a few files.
  Make sure to update `.gitignore` when adding new files.
