## Usage

Run the container of [npm-proxy-cache](https://github.com/runk/npm-proxy-cache)

```
docker run --restart=always --net=host -p 8080:8080 -t kudoz/npm-proxy-cache --name=npm-proxy-cache
```

Add to /etc/rc.local

```
docker start npm-proxy-cache
```

Monitoring

```
docker logs --follow --tail 10  npm-proxy-cache
```

Use it with `npm`, replacing the npm-proxy-cache hostname below with the ip or hostname you have the container above running at.

```
npm --proxy http://npm-proxy-cache:8080 --https-proxy http://npm-proxy-cache:8080 --strict-ssl false install
```
