# 海角解锁器（部署说明）

这个文件夹就是**要上传到 GitHub 的全部内容**，两个文件：

```
index.html           安装页面（手机友好的引导页）
hj_unlock.user.js    主脚本 v4.5.0
```

---

## 一、上传到 GitHub（网页操作，不用命令行）

1. 打开 https://github.com/new
2. **Repository name** 填 `hj-unlock`（或你喜欢的名字）
3. 选 **Public**（私有仓库的 jsDelivr 也能用，但 Pages 需要 Public）
4. 点 **Create repository**
5. 在新仓库页面点 **uploading an existing file**
6. 把 `index.html` 和 `hj_unlock.user.js` **两个文件一起拖进去**
7. 底部点 **Commit changes**

完成。仓库地址大概是：

```
https://github.com/你的用户名/hj-unlock
```

---

## 二、得到安装链接（两种都用得上）

### 方式 A：jsDelivr CDN（推荐，国内速度快）

在仓库建好后**立刻可用**，不需要任何额外设置。把下面链接里的 `你的用户名` 换掉：

```
https://cdn.jsdelivr.net/gh/你的用户名/hj-unlock@main/hj_unlock.user.js
```

**例**：
```
https://cdn.jsdelivr.net/gh/zhangsan/hj-unlock@main/hj_unlock.user.js
```

**优点**：
- 国内访问快（有国内节点）
- 永久有效，跟着仓库走
- 脚本管理器能直接识别 `.user.js` 结尾的链接

**注意**：jsDelivr 有缓存（约 12 小时）。更新脚本后想立刻生效，可以把 `@main` 换成 `@版本号` 或加 `?v=2`，或者等缓存过期。

### 方式 B：GitHub Pages（有安装页面，更好看）

1. 仓库页面 → **Settings** → 左侧 **Pages**
2. **Source** 选 `Deploy from a branch`
3. **Branch** 选 `main`，目录选 `/ (root)`
4. 点 **Save**
5. 等 1~2 分钟，页面顶部会出现：

```
https://你的用户名.github.io/hj-unlock/
```

打开就是那个漂亮的安装页，点按钮直接装脚本。

**缺点**：`github.io` 在国内部分网络下打不开。

---

## 三、发给别人时怎么说

**最省事**：直接发 jsDelivr 链接

```
https://cdn.jsdelivr.net/gh/你的用户名/hj-unlock@main/hj_unlock.user.js
```

让对方在脚本管理器里「从 URL 安装」即可。

**如果对方能打开 GitHub Pages**：发安装页地址更方便（有图文引导）

```
https://你的用户名.github.io/hj-unlock/
```

**别忘了同时给他**：
1. **激活码**（`txx91` 或 `txx78`）
2. 如果凭证失效，让他点 `⚙ 凭证` 填自己买过的 1 金币帖子 id

---

## 四、以后更新脚本怎么办

改了 `hj_unlock.user.js` 之后：

1. 打开 GitHub 仓库
2. 点进 `hj_unlock.user.js`
3. 右上角铅笔图标（Edit）
4. 全选删除 → 粘贴新内容 → Commit

或者直接重新 Upload files 覆盖。

**更新后**：
- Pages 会自动重新部署（1~2 分钟）
- jsDelivr 有缓存，想立刻刷新生效就在链接后加 `?v=日期`，比如 `...user.js?v=20250315`

---

## 五、验证清单

上传后按顺序检查：

| 检查项 | 方法 |
|---|---|
| 仓库有 2 个文件 | 打开仓库首页看 |
| jsDelivr 通 | 浏览器打开 jsDelivr 链接，应该显示脚本文本 |
| Pages 部署成功 | Settings → Pages 显示绿色的 "Your site is live at ..." |
| 手机能装 | 用手机打开链接，脚本管理器弹出安装页 |

---

## 六、常见问题

**Q: jsDelivr 打开是 404？**
仓库名、用户名、分支名（`main` 还是 `master`）三者任一不对都会 404。确认仓库默认分支名，GitHub 新建仓库现在默认是 `main`。

**Q: Pages 显示 404？**
刚 Save 完要等 1~2 分钟。另外确认 `index.html` 在仓库**根目录**，不是子文件夹。

**Q: 脚本装了但不生效？**
- 确认版本号是 4.5.0
- 海角域名每天变，脚本靠特征识别，正常都能过
- 旧版没删干净的话，先删再装
