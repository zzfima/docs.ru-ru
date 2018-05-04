### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a>Для безопасности сообщений WCF теперь могут использоваться TLS1.1 и TLS1.2

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.7 клиенты могут настроить в параметрах конфигурации приложения не только SSL3.0 и TLS1.0, но и TLS1.1 или TLS1.2.|
|Предложение|В .NET Framework 4.7 поддержка TLS1.1 и TLS1.2 в безопасности сообщений WCF по умолчанию отключена. Вы можете включить ее, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config или web.config:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.7|
|Тип|Изменение целевой платформы|

