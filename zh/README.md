# 移动安全开发指南

我们NowSecure花了很多时间攻击移动应用 - 黑客，破解加密，查找缺陷，渗透测试，并寻找存储不安全的敏感数据。 我们这么做是为了帮助开发人员提高应用程序的安全性。 本文件代表了我们与客户和合作伙伴共享的一些知识。 **我们致力于推动全球移动应用安全。**

## 使用本指南

本指南提供了在开发过程中使用的具体建议。 本报告中对攻击和安全建议的描述并不全面或完美，但您将获得实用的建议，您可以使用它们来提高应用程序的安全性。

我们定期修订我们的最佳做法，并欢迎您的[贡献](https://github.com/nowsecure/secure-mobile-development/pulls)。 我们同时会定期从被接受到主存储库中更新本指南并发布在[这里](https://books.nowsecure.com/secure-mobile-development/)。

要了解攻击者可能在您的应用程序上使用的所有攻击方法，请阅读我们的[移动安全入门](primer/mobile-security.md).

### 目录

* [移动安全入门](primer/mobile-security.md)
* [编码实践](coding-practices/README.md)
  * [2.1 增加代码复杂性和使用混淆](coding-practices/code-complexity-and-obfuscation.md)
  * [2.2 避免简单逻辑](coding-practices/avoid-simple-logic.md)
  * [2.3 测试第三方库](coding-practices/test-third-party-libraries.md)
  * [2.4 实施防篡改技术](coding-practices/anti-tamper-techniques.md)
  * [2.5 在内存中安全的存储敏感数据](coding-practices/securely-store-sensitive-data-in-ram.md)
  * [2.6 安全的删除数据](coding-practices/understand-secure-deletion-of-data.md)
  * [2.7 避免敏感数据的查询字符串](coding-practices/avoid-query-string-for-sensitive-data.md)
* [敏感数据处理](sensitive-data/README.md)
  * [3.1 实现安全数据存储](sensitive-data/implement-secure-data-storage.md)
  * [3.2 使用Cookie的安全设置](sensitive-data/use-secure-setting-for-cookies.md)
  * [3.3 完全验证SSL / TLS](sensitive-data/fully-validate-ssl-tls.md)
  * [3.4 防止SSL降级攻击](sensitive-data/protect-against-sslstrip.md)
  * [3.5 限制使用UUID](sensitive-data/limit-use-of-uuid.md)
  * [3.6 谨慎处理地理位置数据](sensitive-data/treat-geolocation-data-carefully.md)
  * [3.7 本地会话超时机制](sensitive-data/institute-local-session-timeout.md)
  * [3.8 使用增强/双因素身份验证](sensitive-data/implement-enhanced-two-factor-authentication.md)
  * [3.9 保护应用程序设置](sensitive-data/protect-application-settings.md)
  * [3.10 隐藏帐号并使用令牌](sensitive-data/hide-account-numbers-and-use-tokens.md)
  * [3.11 使用安全的网络传输方法传输敏感数据](sensitive-data/implement-secure-network-transmission-of-sensitive-data.md)
  * [3.12 验证来自客户端的输入](sensitive-data/validate-input-from-client.md)
  * [3.13 避免将应用程序数据存储在备份中](sensitive-data/avoid-storing-app-data-in-backups.md)
* [缓存与日志](caching-logging/README.md)
  * [4.1 避免缓存应用程序数据](caching-logging/avoid-caching-app-data.md)
  * [4.2 避免崩溃日志](caching-logging/avoid-crash-logs.md)
  * [4.3 限制缓存用户名](caching-logging/limit-caching-of-username.md)
  * [4.4 谨慎管理调试日志](caching-logging/carefully-manage-debug-logs.md)
  * [4.5 注意键盘缓存](caching-logging/be-aware-of-the-keyboard-cache.md)
  * [4.6 注意复制和粘贴](caching-logging/be-aware-of-copy-paste.md)
* [Webviews](webviews/README.md)
  * [5.1 防止frame劫持和点击劫持](webviews/prevent-framing-and-clickjacking.md)
  * [5.2 使用表单令牌保护CSRF](webviews/protect-against-csrf-with-form-tokens.md)
* [iOS](ios/README.md)
  * [6.1 谨慎使用keychain](ios/use-the-keychain-carefully.md)
  * [6.2 避免缓存应用程序快照](ios/avoid-cached-application-snapshots.md)
  * [6.3 保护针对缓冲区溢出的攻击](ios/implement-protections-against-buffer-overflow-attacks.md)
  * [6.4 避免缓存HTTP（S）请求/响应](ios/avoid-caching-https-requests-responses.md)
  * [6.5 应用ATS(App Transport Security)](ios/implement-app-transport-security.md)
  * [6.6 正确应用Touch ID](ios/implement-touch-id-properly.md)
* [Android](android/README.md)
  * [7.1 谨慎配置file permissions](android/implement-file-permissions-carefully.md)
  * [7.2 谨慎实现 Intents](android/implement-intents-carefully.md)
  * [7.3 检查 Activities](android/check-activities.md)
  * [7.4 谨慎使用 Broadcasts](android/use-broadcasts-carefully.md)
  * [7.5 谨慎实现 PendingIntents](android/implement-pendingintents-carefully.md)
  * [7.6 保护应用程序服务](android/protect-application-services.md)
  * [7.7 避免 Intent 嗅探](android/avoid-intent-sniffing.md)
  * [7.8 谨慎实施content providers](android/implement-content-providers-carefully.md)
  * [7.9 遵循WebView最佳实践](android/webview-best-practices.md)
  * [7.10 避免存储缓存的摄像机图像](android/avoid-storing-cached-camera-images.md)
  * [7.11 避免GUI对象缓存](android/avoid-gui-objects-caching.md)
  * [7.12 签名 Android APKs](android/android-apk-signing.md)
* [Servers](servers/README.md)
  * [8.1 实施正确的Web服务器配置](servers/web-server-configuration.md)
  * [8.2 正确配置服务器端SSL](servers/server-side-ssl-configuration.md)
  * [8.3 使用合适的会话管理](servers/web-servers-proper-session-management.md)
  * [8.4 保护和执行Web服务的渗透测试](servers/protect-and-pen-test-web-services.md)
  * [8.5 保护内部资源](servers/protect-internal-resources.md)
