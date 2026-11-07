# Navkit-drivers

NavKit 数据库管理工具的**自有驱动镜像仓库**。

应用（`D:\github\tauri-navicat` → https://github.com/GaoHu1997/Navkit）运行时
通过本仓库的 `raw.githubusercontent.com` 直链下载在用驱动 JAR。源码仓库
（Navkit）不保存任何驱动二进制，只保存 `URL + 大小 + SHA-256` 固定指纹元数据。

## 来源与许可说明

当前托管的三个 JAR 原件来自第三方项目 **dbx**（`t8y2/dbx`）固定提交
`71ce03490dad3c9c3eaaa3bd62863b9a6fcdbb9a`，本仓库为**一次性字节级镜像**：

- 原始字节未做任何修改，原包内许可/签名原样保留；
- dbx 项目自身的许可**不**套用到这些专有驱动内容上；
- 大小与 SHA-256 已与 dbx 固定提交原件逐一核对一致（见下表）。

## 托管清单（应用在用）

| 文件 | 大小 (B) | SHA-256 | NavKit 消费方 |
|---|---|---|---|
| `CacheDB.jar` | 2,233,648 | `2b12827c4e03ce043f10c9651f12206e97bc6fb73d7556451ae97b9d3eb7a29c` | `managed_dbx.rs` vendor `cache`（Caché JDBC 2010.2.3.702） |
| `sundb8-1.0.2.jar` | 567,314 | `d654aa28331888e5b2079f7736a67d3c963ec80140b4775df4af4799da04c733` | `managed_dbx.rs` vendor `sundb`（SUNDB JDBC 8） |
| `oscarJDBC8.jar` | 3,639,760 | `91a05d96da16d57b906cd488cc8c90066fa3878ef17bbf48b88a9d083bafb7be` | `managed_dbx.rs` vendor `oscar`（神通 OSCAR JDBC） |

运行时下载直链格式：
`https://raw.githubusercontent.com/GaoHu1997/Navkit-drivers/main/<文件名>`

## 约定

1. 本仓库只存放 NavKit 运行时在用的驱动镜像；每个文件必须在此表登记
   大小 + SHA-256，并注明原件来源。
2. **不修改已发布的 JAR 字节**：任何变更（包括重新打包）都视为新文件，
   需要新文件名并同步更新 Navkit 源码仓库的固定指纹与来源文案。
3. 新增镜像前先核对原件来源的可核验性；与 dbx 固定提交比对时以
   `71ce03490dad3c9c3eaaa3bd62863b9a6fcdbb9a` 为准。
4. dbx 固定提交上其余内容（gbase8c、uxdb、dameng、goldendb、transwarp），
   应用暂不需要，接入时再镜像（见 Navkit 仓库 `docs/驱动下载来源政策与待办.md`）。
