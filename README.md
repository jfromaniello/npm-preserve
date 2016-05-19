Speed up your npm install operations by caching locally the result.

NPM already has a cache but it will rebuild stuff after is copied from cache.

## Install

```
npm i -g jfromaniello/npm-preserve
```

## Usage

```
#restore or install from scratch
npm-preserve-restore my-project /tmp || npm install

# npm test ..etc

#cache the stuff after you are done
npm-preserve-cache my-project /tmp

# npm prune --production
# deploy
```

## License

MIT 2016 - José F. Romaniello
