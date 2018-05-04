### <a name="signedxmlgetpublickey-returns-rsacng-on-net462-or-lightup-without-retargeting-change"></a>SignedXml.GetPublicKey возвращает RSACng в net462 (или lightup) без изменения целевой платформы

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.6.2 конкретный тип объекта, возвращаемого методом <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType>, изменен (без особенностей) с реализации CryptoServiceProvider на реализацию Cng. Это связано с изменениями реализации, предусматривающими использование <code>certificate.PublicKey.Key</code> вместо внутреннего <code>certificate.GetAnyPublicKey</code> с переадресацией к <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.|
|Предложение|Начиная с приложений, выполняющихся в .NET Framework 4.7.1, вы можете использовать реализацию CryptoServiceProvider, используемую по умолчанию на платформе .NET Framework 4.6.1 и более ранних версий, добавив следующую конфигурацию в раздел [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.Xml.SignedXmlUseLegacyCertificatePrivateKey=true&quot; /&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.6.2|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Security.Cryptography.Xml.SignedXml.CheckSignatureReturningKey(System.Security.Cryptography.AsymmetricAlgorithm@)?displayProperty=nameWithType></li></ul>|

