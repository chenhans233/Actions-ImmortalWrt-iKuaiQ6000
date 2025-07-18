**English** | [中文](https://p3terx.com/archives/build-openwrt-with-github-actions.html)

[![LICENSE](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square&label=LICENSE)](https://github.com/P3TERX/Actions-OpenWrt/blob/master/LICENSE)
# A fork of Actions-OpenWrt 
A template for building OpenWrt with GitHub Actions

(Under Construction...)
母项目还在完善中

本项目仅供个人学习，不保证固件稳定性和兼容性，不要用于生产环境。
### 注意！
固件只会在 _IK-Q6000_ 上测试，默认OpenWrt(ImmortalWrt)-110m分区表，请自行寻找合适的类AX6000 U-Boot，用[mtk_uartboot工具注入](https://www.openwrt.pro/post-656.html)后备份完整NAND，并刷写分区表（建议用合适的第三方不死U-Boot覆盖掉原厂的U-Boot分区）。

```
root@ImmortalWrt:~# cat /proc/mtd
dev:    size   erasesize  name
mtd0: 00100000 00020000 "BL2"
mtd1: 00040000 00020000 "Nvram"
mtd2: 00040000 00020000 "Bdata"
mtd3: 00200000 00020000 "Factory"
mtd4: 00200000 00020000 "FIP"
mtd5: 00040000 00020000 "crash"
mtd6: 00040000 00020000 "crash_log"
mtd7: 06e00000 00020000 "ubi"
```
## 特别鸣谢
Special thanks to...
- [dailook对原厂IK-Q6000适配](https://github.com/dailook/lede)
- [hanwckf的mt-wifi](https://github.com/hanwckf/immortalwrt-mt798x)
- [padavanonly的6.6.xx patching](https://github.com/padavanonly)


## Usage

- Click the [Use this template](https://github.com/P3TERX/Actions-OpenWrt/generate) button to create a new repository.
- Generate `.config` files using [Lean's OpenWrt](https://github.com/coolsnowwolf/lede) source code. ( You can change it through environment variables in the workflow file. )
- Push `.config` file to the GitHub repository.
- Select `Build OpenWrt` on the Actions page.
- Click the `Run workflow` button.
- When the build is complete, click the `Artifacts` button in the upper right corner of the Actions page to download the binaries.

## Tips

- It may take a long time to create a `.config` file and build the OpenWrt firmware. Thus, before create repository to build your own firmware, you may check out if others have already built it which meet your needs by simply [search `Actions-Openwrt` in GitHub](https://github.com/search?q=Actions-openwrt).
- Add some meta info of your built firmware (such as firmware architecture and installed packages) to your repository introduction, this will save others' time.

## Credits

- [Microsoft Azure](https://azure.microsoft.com)
- [GitHub Actions](https://github.com/features/actions)
- [OpenWrt](https://github.com/openwrt/openwrt)
- [coolsnowwolf/lede](https://github.com/coolsnowwolf/lede)
- [Mikubill/transfer](https://github.com/Mikubill/transfer)
- [softprops/action-gh-release](https://github.com/softprops/action-gh-release)
- [Mattraks/delete-workflow-runs](https://github.com/Mattraks/delete-workflow-runs)
- [dev-drprasad/delete-older-releases](https://github.com/dev-drprasad/delete-older-releases)
- [peter-evans/repository-dispatch](https://github.com/peter-evans/repository-dispatch)

## License

[MIT](https://github.com/P3TERX/Actions-OpenWrt/blob/main/LICENSE) © [**P3TERX**](https://p3terx.com)
