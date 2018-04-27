### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a>RSACng.VerifyHash теперь возвращает значение False при любом сбое проверки

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.6.2 этот метод возвращает <strong>False</strong>, если сама подпись неверно форматирована. Теперь он возвращает значение false при любом сбое проверки. В .NET Framework 4.6 и 4.6.1 этот метод выдает <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>, если сама подпись имеет неправильный формат.|
|Предложение|Любой код, выполнение которого зависит от обработки <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>, следует изменить так, чтобы он выполнялся, когда проверка завершается неудачей и метод возвращает <strong>False</strong>.|
|Область|Дополнительный номер|
|Версия|4.6.2|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|

