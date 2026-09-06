# gaokun-android / crDroid 16.0

仅维护设备、自有工具和打过补丁的 fork；其余源码跟随 crDroid 上游，不锁定 commit。

- `00-remotes.xml`：声明源码与 MindTheGapps 远端。
- `01-removes.xml`：移除需要替换的上游项目。
- `02-gaokun3.xml`：添加本组织的仓库；内核跟随 `linux-rolling-stable`，浅克隆。

`repo` 按文件名顺序自动加载这三个 XML，无需 `include`。crDroid 未包含的 `device/linaro/dragonboard` 和 `vendor/gapps` 也在 `02` 中声明。

## 使用

```sh
repo init -u https://github.com/crdroidandroid/android.git -b 16.0 --depth=1
git clone -b 16.0 https://github.com/gaokun-android/local_manifests.git .repo/local_manifests
repo sync -c --no-tags -j8
```
