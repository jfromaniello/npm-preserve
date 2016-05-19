Speed up your npm install operations by caching locally the result.

NPM already has a cache but it will rebuild stuff after is copied from cache.

## Install

```
npm i -g jfromaniello/npm-preserve
```

## Usage

```
#restore or install from scratch
npm-preserve-restore || npm install

# npm test ..etc

#cache the stuff after you are done
npm-preserve-cache

# npm prune --production
# deploy
```

## How it works

`npm-preserve-cache`  computes an md5 hashsum of package.json's `devDepdencies` and `dependencies` plus all the content `npm-shrinkwrap`. Then it stores the `node_modules` directory in the current dir as `/tmp/project-name-HASHSUM.tar.gz`.

`npm-preserve-restore` computes an md5 hashsum of package.json's `devDepdencies` and `dependencies` plus all the content `npm-shrinkwrap`. Then it search the tar.gz file named `/tmp/project-name-HASHSUM.tar.gz` if this file exists, it will restore `node_modules` from this file and exit with status code 0, if it doesn't exists it will return code 1.

`project-name` in the file name is the name of the package.json in the current directory.

`npm-preserve-cache` and `npm-preserve-restore` uses /tmp as default caching directory, you could also use a different directory with:

```
npm-preserve-cache /foo/bar
npm-preserve-restore /foo/bar
```

## License

MIT 2016 - José F. Romaniello
