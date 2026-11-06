# share_movie

原视频无损备份。时长约 75 分 10 秒，1280 × 720，MOV（H.264 / AAC）。

## 下载

前往 [视频下载页面](https://github.com/ManechoLIU/share_movie/releases/tag/movie-2026-11-06)，下载以下两个分卷到同一个文件夹：

- `share_movie.mov.part01`
- `share_movie.mov.part02`

原视频大小为 3,477,551,085 字节，超过 GitHub 单个 Release 附件的 2 GiB 限制，因此使用分卷存储。分卷需要合并后播放。

## 合并视频

macOS / Linux：

```sh
cat share_movie.mov.part01 share_movie.mov.part02 > share_movie.mov
```

Windows 命令提示符（CMD）：

```bat
copy /b share_movie.mov.part01+share_movie.mov.part02 share_movie.mov
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
