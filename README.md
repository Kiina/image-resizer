# Image Resizer
An automatic image Resizer forked from [Minios Thumbnailer example](https://github.com/minio/thumbnailer). It can auto resize your jpgs and create webps for them.
It's super basic code and kinda sloppy, but it does what it should do. Feel free to contribute. It doesn't support authentication yet, so you probably don't want to expose it openly.

## Dependencies
Dependencies are managed by [npm](https://npm.org) use `npm install`.

```sh
npm install
```

## Configure
Please edit the configs in `config/` with your local parameters.


## Run
Once configured proceed to run. There is a docker-compose.yml as an example. Set your keys and run the container with `docker-compose up`.
Activate the hook via mc kinda like this: `mc event add minio/bucketname arn:minio:sqs::_:webhook --event put --suffix .jpg`
Now you can upload an image to your minio and see it converted.

```sh
node_1   | Successfully uploaded "a1a967b139071d7c4fd0acbbbf310d6a"
node_1   | Successfully uploaded "61cbe2d150ecc39b3abc36b9d0d4a864"
node_1   | Successfully uploaded "6d948aaf050ba90b3e7919617fb20fdf"
node_1   | Successfully uploaded "84dca44d5b2922cde7e3fba88a6e1083"
```

Your generated files will have the format of filename-size.jpg/webp. Don't use files with spaces as it breaks.
