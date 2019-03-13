# qiita-stocker-docker

[Mindexer](https://www.mindexer.net) で共通利用するDockerfileを管理します。

## [nekochans/laravel-build](https://cloud.docker.com/u/nekochans/repository/docker/nekochans/laravel-build)

[![dockeri.co](https://dockeri.co/image/nekochans/laravel-build)](https://hub.docker.com/r/nekochans/laravel-build)

### イメージの更新方法

Dockerfileからイメージを作成します。

```bash
cd laravel-build/
docker build -t nekochans/laravel-build .
```

以下のコマンドで動作確認をします。

```bash
docker run -it nekochans/laravel-build php -v
docker run -it nekochans/laravel-build node -v
docker run -it nekochans/laravel-build npm --version
docker run -it nekochans/laravel-build yarn --version
```

各ミドルウェアのバージョンが表示されれば成功です。

GitHub上でタグをPushするとDocker Hub上にも反映されます。

例えばこのようなタグを設定すると・・・

```
git tag -a v1.0.0 -m "release version v1.0.0"
git push origin tags/v1.0.0
```

Docker Hub上では `1.0.0` のタグが自動で作成されます。（`v1.0.0` のように v が必要なので注意）
