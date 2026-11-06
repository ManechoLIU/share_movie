# share_movie

原视频无损备份。时长约 75 分 10 秒，1280 × 720，MOV（H.264 / AAC）。

## 下载

前往 [视频下载页面](https://github.com/ManechoLIU/share_movie/releases/tag/movie-2026-11-06)，下载全部 52 个分卷到同一个文件夹：`share_movie.mov.part001` 至 `share_movie.mov.part052`。

安装了 GitHub CLI 时，可以一次下载全部分卷：

```sh
gh release download movie-2026-11-06 --repo ManechoLIU/share_movie --pattern 'share_movie.mov.part*' --dir share_movie_parts
```

随后进入 `share_movie_parts` 文件夹执行下面的合并命令。

原视频大小为 3,477,551,085 字节，超过 GitHub 单个 Release 附件的 2 GiB 限制，同时上传连接对大文件不稳定，因此使用每卷最多 64 MiB 的分卷存储。分卷需要合并后播放。

## 合并视频

macOS / Linux：

```sh
cat share_movie.mov.part[0-9][0-9][0-9] > share_movie.mov
```

Windows 命令提示符（CMD）：

```bat
copy /b share_movie.mov.part* share_movie.mov
```

合并只是按顺序拼接文件，没有重新编码，画质和声音与原视频完全一致。

## 校验

合并后文件的 SHA-256：

```text
670a6c7621f115c1e53304121808485ad3c49a61862ad64810e491e780da22f6
```

macOS：`shasum -a 256 share_movie.mov`  
Linux：`sha256sum share_movie.mov`  
Windows PowerShell：`Get-FileHash share_movie.mov -Algorithm SHA256`

分卷校验值及大小见 Release 中的 `manifest.json` 和 `SHA256SUMS.txt`。
