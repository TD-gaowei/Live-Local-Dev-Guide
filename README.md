# Live 项目本地运行指南

## 需要改动下面几个文件

enviorment.env

```text
// export const isDevelopmentEnv = process.env.NODE_ENV === "development";
export const isDevelopmentEnv = false;
// export const isAtlasMode = window.location.href.indexOf("/atlas") > -1;
export const isAtlasMode = true;

```
