# Moment App 配置仓库

这是 Moment 应用的远程配置仓库，用于动态管理应用支持的平台配置。

## 配置文件说明

### app_schemes.json

主配置文件，包含所有支持的平台信息。

#### 配置结构

```json
{
  "version": "1.0.0",                    // 配置版本号
  "last_updated": "2025-06-22T10:30:00Z", // 最后更新时间
  "min_app_version": "1.0.0",            // 最低支持的应用版本
  "update_priority": "normal",           // 更新优先级 (low/normal/high/critical)
  "changelog": "初始版本配置",            // 版本变更说明
  "platforms": [...]                    // 平台配置列表
}
```

#### 平台配置字段

- `id`: 平台唯一标识符
- `package`: Android 应用包名
- `scheme`: URL Scheme 跳转链接
- `fallback`: 网页版备用链接
- `theme_color`: 平台主题色
- `enabled`: 是否启用该平台
- `priority`: 显示优先级（数字越小优先级越高）
- `added_version`: 添加该平台的版本
- `last_updated`: 平台配置最后更新日期

## 更新流程

1. 修改 `app_schemes.json` 配置文件
2. 更新 `version` 字段（遵循语义化版本号）
3. 更新 `last_updated` 时间戳
4. 填写 `changelog` 变更说明
5. 提交到 main 分支，GitHub Pages 会自动部署

## 版本管理

使用语义化版本号：
- 主版本号：不兼容的重大变更
- 次版本号：向下兼容的功能新增  
- 修订号：向下兼容的问题修正

## 支持的平台

当前支持以下平台：

1. 小红书 (xhs)
2. 知乎 (zhihu)
3. 大众点评 (dianping)
4. 抖音 (douyin)
5. 哔哩哔哩 (bilibili)
6. 拼多多 (pinduoduo)
7. 美团 (meituan)
8. 携程 (ctrip)
9. 豆瓣 (douban)

## 注意事项

- 配置更新后，Moment 应用会在下次启动时自动检查更新
- 用户也可以在设置页面手动检查更新
- 请确保 JSON 格式正确，避免应用解析失败
- 新增平台时请测试 URL Scheme 的有效性
