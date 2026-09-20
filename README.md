# Portainer 1.24.2 中文界面文件

> [!IMPORTANT]
> 本仓库已经归档，仅适用于旧版 Portainer 1.24.2，不支持当前的 Portainer CE。项目不再维护，也不会提供安全更新。

本仓库保存 Portainer 1.24.2 的中文化 Web 静态资源。中文界面文件来源于 CecOS CaaS 容器云平台，并针对 Portainer 1.24.2 做了适配。

## 使用方法

将仓库内容作为 Portainer 的 `/public` 目录挂载。以下命令仅用于兼容旧环境：

```bash
docker volume create portainer_data

docker run -d \
  -p 9000:9000 \
  --name portainer \
  --restart always \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v portainer_data:/data \
  -v /root/public:/public \
  portainer/portainer:1.24.2
```

不要使用 `portainer/portainer:latest`，否则可能拉取与这些静态资源不兼容的版本。

## 安全提示

Portainer 1.24.2 已经过时，不建议直接暴露到互联网。继续使用时应限制管理端口的访问来源，并优先规划迁移到仍受支持的版本。

## 许可证

中文化文件按其来源声明采用 GNU General Public License v2.0。Portainer 本体、字体、图片及其他第三方资源仍分别遵循各自原有许可证，详情见 [LICENSE](LICENSE)。
