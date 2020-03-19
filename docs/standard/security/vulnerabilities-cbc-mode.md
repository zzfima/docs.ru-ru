---
title: Уязвимость расшифровки CBC
description: Узнайте, как обнаружить и уменьшить уязвимости времени с помощью симметричной расшифровки cipher-Block-Chaining (CBC) с помощью обивки.
ms.date: 06/12/2018
author: blowdart
ms.openlocfilehash: 47520ea4c9c7d0ef4d79378c93c6ce1f2ba7dd6d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186098"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a>Уязвимости в учете времени при симметричной расшифровке в режиме CBC с использованием заполнения

Microsoft считает, что это больше не безопасно расшифровать данные, зашифрованные с cipher-Block-Chaining (CBC) режим симметричного шифрования, когда проверяемая обивка была применена без предварительного обеспечения целостности шифровального текста, за исключением очень конкретных Обстоятельствах. Это решение основано на известных в настоящее время криптографических исследованиях.

## <a name="introduction"></a>Введение

Атака оракула является типом атаки на зашифрованные данные, который позволяет злоумышленнику расшифровать содержимое данных, не зная ключа.

Оракул относится к "рассказать", который дает злоумышленнику информацию о том, является ли действие, которое они исполняют, правильным или нет. Представьте себе, играя в настольную или карточную игру с ребенком. Когда их лицо загорается с широкой улыбкой, потому что они думают, что они собираются сделать хороший ход, это оракул. Вы, как противник, можете использовать этот оракул, чтобы спланировать свой следующий шаг соответствующим образом.

Обивка — это специфический криптографический термин. Некоторые шифры, которые являются алгоритмами, используемыми для шифрования данных, работают на блоках данных, где каждый блок имеет фиксированный размер. Если данные, которые вы хотите шифровать, не имеют нужного размера для заполнения блоков, ваши данные заполняются до тех пор, пока они не будут заполнены. Многие формы обивки требуют, чтобы обивка всегда присутствовала, даже если исходный вход был нужного размера. Это позволяет всегда безопасно удалять обивку при расшифровке.

Объединяя две вещи, реализация программного обеспечения с помощью оракула с обивкой показывает, имеет ли расшифрованные данные действительную обивку. Оракул может быть что-то же просто, как возвращение значения, которое говорит "Недействительной обивки" или что-то более сложное, как с измеримо разное время для обработки действительного блока, в отличие от недействительного блока.

Шифры на основе блоков имеют другое свойство, называемое режимом, которое определяет отношение данных в первом блоке к данным во втором блоке и так далее. Одним из наиболее часто используемых режимов является CBC. CBC вводит первоначальный случайный блок, известный как Вектор инициализации (IV), и объединяет предыдущий блок с результатом статического шифрования, чтобы сделать его таким, что шифрование одного и того же сообщения с тем же ключом не всегда производит тот же зашифрованный выход.

Злоумышленник может использовать оракула обивки, в сочетании с тем, как структурированы данные CBC, для отправки слегка измененных сообщений в код, который предоставляет оракула, и продолжать отправлять данные, пока оракул говорит им, что данные верны. Из этого ответа, злоумышленник может расшифровать сообщение байт байтом.

Современные компьютерные сети имеют такое высокое качество, что злоумышленник может обнаружить очень небольшие (менее 0,1 мс) различия во времени выполнения на удаленных системах.Приложения, которые предполагают, что успешная расшифровка может произойти только тогда, когда данные не были подделаны, могут быть уязвимы для атак с помощью инструментов, предназначенных для наблюдения за различиями в успешной и неудачной расшифровке. Хотя в некоторых языках или библиотеках разница во времени может быть более значительной, чем в других, теперь считается, что это практическая угроза для всех языков и библиотек, когда учитывается реакция приложения на сбой.

Эта атака зависит от способности изменять зашифрованные данные и тестировать результат с помощью оракула. Единственный способ полностью смягчить атаку — обнаружить изменения в зашифрованных данных и отказаться от выполнения каких-либо действий по ней. Стандартный способ сделать это заключается в создании подписи для данных и проверке этой подписи до выполнения каких-либо операций. Подпись должна быть проверяемой, она не может быть создана злоумышленником, в противном случае они изменят зашифрованные данные, а затем вычислят новую подпись на основе измененных данных. Один из распространенных типов соответствующей подписи известен как код проверки подлинности ключей (HMAC). HMAC отличается от чексум в том, что он принимает секретный ключ, известный только для лица, производящего HMAC и лицо, проверяющее его. Без владения ключом, вы не можете произвести правильный HMAC. Когда вы получаете свои данные, вы будете принимать зашифрованные данные, самостоятельно вычислить HMAC с помощью секретного ключа вы и отправитель доля, а затем сравнить HMAC они послали против того, что вы вычислили. Это сравнение должно быть постоянным временем, в противном случае вы добавили другой обнаруживаемый оракул, что позволяет другой тип атаки.

Таким образом, чтобы безопасно использовать проложенные шифры блоков CBC, необходимо объединить их с HMAC (или другой проверкой целостности данных), которую вы проверяете с помощью постоянного сравнения времени, прежде чем пытаться расшифровать данные. Поскольку все измененные сообщения занимают одинаковое количество времени для получения ответа, атака предотвращается.

## <a name="who-is-vulnerable"></a>Кто уязвим

Эта уязвимость применяется как к управляемым, так и к нативным приложениям, которые выполняют свое собственное шифрование и расшифровку. Это включает в себя, например:

- Приложение, которое шифрует файл cookie для последующей расшифровки на сервере.
- Приложение базы данных, которое предоставляет пользователям возможность вставлять данные в таблицу, столбцы которой позже расшифровываются.
- Приложение для передачи данных, которое опирается на шифрование с помощью общего ключа для защиты данных в пути.
- Приложение, которое шифрует и расшифровывает сообщения "внутри" туннеля TLS.

Обратите внимание, что использование TLS в одиночку не может защитить вас в этих сценариях.

Уязвимое приложение:

- Расшифровывает данные с помощью режима шифра CBC с проверяемым режимом обивки, таким как PKCS-7 или ANSI X.923.
- Выполняет расшифровку без проведения проверки целостности данных (через MAC или асимметричную цифровую подпись).

Это также относится к приложениям, построенным поверх абстракций поверх этих примитивов, таких как cryptographic Message Syntax (PKCS-7/CMS) EnvelopedData.

## <a name="related-areas-of-concern"></a>Смежные области, вызывающие озабоченность

Исследования привели Microsoft быть дополнительно обеспокоены CBC сообщения, которые мягкие с ISO 10126 эквивалент обивка, когда сообщение имеет хорошо известную или предсказуемую структуру колонтитула. Например, контент, подготовленный по правилам Рекомендации по синтаксису и обработке шифрования W3C XML (xmlenc, EncryptedXml). В то время как руководство W3C подписать сообщение, то шифрование было сочтено целесообразным в то время, Microsoft теперь рекомендует всегда делать шифрование-то-знак.

Разработчики приложений всегда должны помнить о проверке применимости ключа асимметричной подписи, так как между асимметричным ключом и произвольным сообщением нет присущей доверительной связи.

## <a name="details"></a>Сведения

Исторически сложилось так, что существует консенсус в отношении того, что важно как шифровать, так и аутентифицировать важные данные, используя такие средства, как подписи HMAC или RSA. Однако было менее четкое руководство относительно того, как секвенировать операции шифрования и проверки подлинности. Из-за уязвимости, подробно описанной в этой статье, руководство Корпорации Майкрософт теперь всегда использует парадигму «шифровать-то знак». То есть сначала шифровать данные с помощью симметричного ключа, затем вычислить MAC или асимметричную подпись над шифровейтом (зашифрованными данными). При расшифровке данных выполните обратное. Сначала подтвердите MAC или подпись шифровального текста, а затем расшифровать его.

Класс уязвимостей, известный как "атаки оракулов", как известно, существует уже более 10 лет. Эти уязвимости позволяют злоумышленнику расшифровать данные, зашифрованные симметричными алгоритмами блоков, такими как AES и 3DES, используя не более 4096 попыток на блок данных. Эти уязвимости используют тот факт, что шифры блоков наиболее часто используются с проверяемыми данными обивки в конце. Выяснилось, что если злоумышленник может взломать шифровальст и выяснить, вызвалли ли подделка ошибка в формате обивки в конце, злоумышленник может расшифровать данные.

Первоначально практические атаки основывались на сервисах, которые возвращали различные коды ошибок в зависимости от того, была ли обивка допустимой, например, ASP.NET уязвимости [MS10-070.](/security-updates/SecurityBulletins/2010/ms10-070) Тем не менее, Microsoft теперь считает, что это практично проводить аналогичные атаки, используя только различия во времени между обработкой действительным и недействительным обивка.

При условии, что в схеме шифрования используется подпись и что проверка подписи выполняется с фиксированным временем выполнения данной длины данных (независимо от содержимого), целостность данных может быть проверена без испускания какой-либо информации злоумышленнику через [боковой канал.](https://en.wikipedia.org/wiki/Side-channel_attack) Поскольку проверка целостности отвергает любые подделанные сообщения, угроза оракула смягчается.

## <a name="guidance"></a>Руководство

Прежде всего, корпорация Майкрософт рекомендует передавать любые данные, имеющие конфиденциальные потребности, через Transport Layer Security (TLS), преемника уровня безопасных розеток (SSL).

Далее проанализируйте приложение на:

- Понять, какое именно шифрование вы выполняете и какое шифрование обеспечивается платформами и AA, которые вы используете.
- Будьте уверены, что каждое использование на каждом слое симметричного [алгоритма шифровирования блока,](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)таких как AES и 3DES, в режиме CBC включает в себя использование секретной проверки целостности данных (асимметричная подпись, HMAC, или изменить режим шифра на [режим аутентифицированного шифрования](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE), таких как GCM или CCM).

Основываясь на текущих исследованиях, принято считать, что, когда аутентификация и шифрование выполняются независимо для режимов шифрования, не связанных с AE, аутентификация шифровальщика (шифровальщика-то-знака) является наилучшим общим вариантом. Тем не менее, нет универсального правильного ответа на криптографию, и это обобщение не так хорошо, как направленные советы от профессионального криптографа.

Приложениям, которые не могут изменить формат обмена сообщениями, но выполняют неподтвердилую расшифровку CBC, рекомендуется попытаться включить в них такие меры, как:

- Расшифровка без разрешения расшифровщика для проверки или удаления обивки:
  - Любая прикладная обивка все еще должна быть удалена или проигнорирована, вы перемещаете бремя в ваше приложение.
  - Преимущество заключается в том, что проверка и удаление обивки могут быть включены в другую логику проверки данных приложения. Если проверка заполнения и проверка данных может быть выполнена в постоянное время, угроза уменьшается.
  - Поскольку интерпретация обивки изменяет предполагаемую длину сообщения, информация о сроках все еще может быть излучаемая в соответствии с этим подходом информация о сроках.
- Измените режим заполнения расшифровки на ISO10126:
  - ISO10126 обивка расшифровки совместима как с PKCS7 шифрования обивка и ANSIX923 шифрования обивка.
  - Изменение режима уменьшает знание оракула до 1 байт вместо всего блока. Однако, если содержимое имеет хорошо известную колонтитул, например, закрывающий элемент XML, связанные атаки могут продолжать атаковать остальную часть сообщения.
  - Это также не предотвращает восстановление простого текста в ситуациях, когда злоумышленник может принудить один и тот же простой текст к шифрованию несколько раз с различным смещением сообщений.
- Ворота оценки расшифровки вызова, чтобы ослабить сигнал времени:
  - Вычисление времени удержания должно иметь минимум больше максимального времени операции расшифровки для любого сегмента данных, содержащего обивку.
  - Расчеты времени должны быть сделаны в соответствии с руководством в <xref:System.Environment.TickCount?displayProperty=nameWithType> [приобретении штампов с высоким разрешением,](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps)а не с помощью (при условии опрокидывания/ переполнения) или вычитания двух системных меток времени (при условии ошибок корректировки NTP).
  - Расчеты времени должны включать в себя операцию дешифрования, включая все потенциальные исключения в управляемых приложениях или приложениях СЗ, а не просто накладываются на конец.
  - Если успех или неудача еще не определены, ворота времени должны вернуть сбой, когда он истекает.
- Службы, выполняющие неподтвердилую дешифровку, должны иметь возможность мониторинга, чтобы обнаружить, что произошло наводнение "недействительных" сообщений.
  - Имейте в виду, что этот сигнал несет в себе как ложные срабатывания (законно поврежденные данные), так и ложные негативы (распространение атаки в течение достаточно длительного времени, чтобы избежать обнаружения).

## <a name="finding-vulnerable-code---native-applications"></a>Поиск уязвимого кода - родные приложения

Для программ, построенных на фоне библиотеки Windows Cryptography: Next Generation (CNG):

- Вызов расшифровки в [BCryptDecrypt,](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt)с указанием флага. `BCRYPT_BLOCK_PADDING`
- Ключевая ручка была инициализирована, позвонив [bCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) с [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) установленной на `BCRYPT_CHAIN_MODE_CBC`.
  - Поскольку `BCRYPT_CHAIN_MODE_CBC` это значение по умолчанию, пострадавному коду, возможно, не было назначено какое-либо значение для. `BCRYPT_CHAINING_MODE`

Для программ, построенных на фоне более старого криптографического API Windows:

- Вызов расшифровки является [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) с `Final=TRUE`.
- Ключевая ручка была инициализирована [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) путем `CRYPT_MODE_CBC`вызова [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) с KP_MODE установлен на .
  - Поскольку `CRYPT_MODE_CBC` это значение по умолчанию, пострадавному коду, возможно, не было назначено какое-либо значение для. `KP_MODE`

## <a name="finding-vulnerable-code---managed-applications"></a>Поиск уязвимого кода - управляемые приложения

- Вызов расшифровки <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> к <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> или <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>методам на .
  - Это включает в себя следующие типы производных в пределах .NET, но может также включать сторонние типы:
    - <xref:System.Security.Cryptography.Aes>
    - <xref:System.Security.Cryptography.AesCng>
    - <xref:System.Security.Cryptography.AesCryptoServiceProvider>
    - <xref:System.Security.Cryptography.AesManaged>
    - <xref:System.Security.Cryptography.DES>
    - <xref:System.Security.Cryptography.DESCryptoServiceProvider>
    - <xref:System.Security.Cryptography.RC2>
    - <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
    - <xref:System.Security.Cryptography.Rijndael>
    - <xref:System.Security.Cryptography.RijndaelManaged>
    - <xref:System.Security.Cryptography.TripleDES>
    - <xref:System.Security.Cryptography.TripleDESCng>
    - <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>
- Свойство <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> было <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>установлено, чтобы, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>или <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.
  - Поскольку <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> это значение по умолчанию, <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> пострадавший код, возможно, никогда не присвоил свойство.
- Свойство <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> было установлено для<xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>
  - Поскольку <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> это значение по умолчанию, <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> пострадавший код, возможно, никогда не присвоил свойство.

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a>Поиск уязвимого кода - криптографический синтаксис сообщения

Непроверенное сообщение CMS EnvelopedData, зашифрованное содержимое которого использует режим CBC AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) или RC2 (1.2.840.113549.3.2) уязвимы, а также сообщения, использующие любые другие алгоритмы шифровирования блоков в режиме CBC.

Хотя шифры потоков не подвержены этой уязвимости, корпорация Майкрософт рекомендует всегда проверять подлинность данных при проверке значения ContentEncryptionAlgorithm.

Для управляемых приложений капля CMS EnvelopedData может быть обнаружена как любое значение, которое передается. <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>

Для нативных приложений, CMS EnvelopedData капля может быть обнаружена в качестве любого `CMSG_ENVELOPED` значения, предоставляемого на ручку `CMSG_CTRL_DECRYPT` CMS через [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) которого в результате [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) и / или ручка CMS позже отправляется инструкция через [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).

## <a name="vulnerable-code-example---managed"></a>Уязвимый пример кода - управляемый

Этот метод считывает файл ы cookie и расшифровывает его, и проверка целостности данных не видна. Таким образом, содержимое файла cookie, прочитанный этим методом, может быть атаковано пользователем, получившим его, или любым злоумышленником, получившим зашифрованное значение cookie.

```csharp
private byte[] DecryptCookie(string cookieName)
{
    HttpCookie cookie = Request.Cookies[cookieName];

    if (cookie == null)
    {
        return null;
    }

    using (ICryptoTransform decryptor = _aes.CreateDecryptor())
    using (MemoryStream memoryStream = new MemoryStream())
    using (CryptoStream cryptoStream =
        new CryptoStream(memoryStream, decryptor, CryptoStreamMode.Write))
    {
        byte[] readCookie = Convert.FromBase64String(cookie.Value);
        cryptoStream.Write(readCookie, 0, readCookie.Length);
        cryptoStream.FlushFinalBlock();
        return memoryStream.ToArray();
    }
}
```

## <a name="example-code-following-recommended-practices---managed"></a>Пример кода, следуя рекомендуемой практике - управляемый

Следующий пример кода использует нестандартный формат сообщения

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

где `cipher_algorithm_id` идентификаторы и `hmac_algorithm_id` идентификаторы алгоритмов являются локальными (нестандартными) представлениями этих алгоритмов. Эти идентификаторы могут иметь смысл в других частях существующего протокола обмена сообщениями, а не в виде голого скатированного байтстрима.

Этот пример также использует один мастер-ключ для получения ключа шифрования и ключа HMAC. Это предусмотрено как в качестве удобства для превращения познавательного ключа приложения в двойной ключ приложения, и поощрять сохранение двух ключей в качестве различных значений. Это также гарантирует, что ключ и ключ шифрования HMAC не могут выйти из синхронизации.

Этот образец не <xref:System.IO.Stream> принимает для шифрования или расшифровки. Текущий формат данных затрудняет шифрование `hmac_tag` с одним проходом, поскольку значение предшествует шифроводному тексту. Тем не менее, этот формат был выбран потому, что он сохраняет все элементы фиксированного размера в начале, чтобы держать парсер проще. При этом формате данных возможна расшифровка с одним проходом, хотя исполнителю рекомендуется позвонить в GetHashAndReset и проверить результат перед вызовом TransformFinalBlock. Если потоковое шифрование важно, то может потребоваться другой режим AE.

```csharp
// ==++==
//
//   Copyright (c) Microsoft Corporation.  All rights reserved.
//
//   Shared under the terms of the Microsoft Public License,
//   https://opensource.org/licenses/MS-PL
//
// ==--==

using System;
using System.Diagnostics;
using System.IO;
using System.Runtime.CompilerServices;
using System.Security.Cryptography;

namespace Microsoft.Examples.Cryptography
{
    public enum AeCipher : byte
    {
        Unknown,
        Aes256CbcPkcs7,
    }

    public enum AeMac : byte
    {
        Unknown,
        HMACSHA256,
        HMACSHA384,
    }

    /// <summary>
    /// Provides extension methods to make HashAlgorithm look like .NET Core's
    /// IncrementalHash
    /// </summary>
    internal static class IncrementalHashExtensions
    {
        public static void AppendData(this HashAlgorithm hash, byte[] data)
        {
            hash.TransformBlock(data, 0, data.Length, null, 0);
        }

        public static void AppendData(
            this HashAlgorithm hash,
            byte[] data,
            int offset,
            int length)
        {
            hash.TransformBlock(data, offset, length, null, 0);
        }

        public static byte[] GetHashAndReset(this HashAlgorithm hash)
        {
            hash.TransformFinalBlock(Array.Empty<byte>(), 0, 0);
            return hash.Hash;
        }
    }

    public static partial class AuthenticatedEncryption
    {
        /// <summary>
        /// Use <paramref name="masterKey"/> to derive two keys (one cipher, one HMAC)
        /// to provide authenticated encryption for <paramref name="message"/>.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="message">The message to encrypt</param>
        /// <returns>
        /// A concatenation of
        /// [cipher algorithm+chainmode+padding][mac algorithm][authtag][IV][ciphertext],
        /// suitable to be passed to <see cref="Decrypt"/>.
        /// </returns>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or bigger) value generated
        /// by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>.
        /// This implementation chooses to block deficient inputs by length, but does not
        /// make any attempt at discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase)
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Encrypt(byte[] masterKey, byte[] message)
        {
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (message == null)
                throw new ArgumentNullException(nameof(message));

            // First, choose an encryption scheme.
            AeCipher aeCipher = AeCipher.Aes256CbcPkcs7;

            // Second, choose an authentication (message integrity) scheme.
            //
            // In this example we use the master key length to change from HMACSHA256 to
            // HMACSHA384, but that is completely arbitrary. This mostly represents a
            // "cryptographic needs change over time" scenario.
            AeMac aeMac = masterKey.Length < 48 ? AeMac.HMACSHA256 : AeMac.HMACSHA384;

            // It's good to be able to identify what choices were made when a message was
            // encrypted, so that the message can later be decrypted. This allows for
            // future versions to add support for new encryption schemes, but still be
            // able to read old data. A practice known as "cryptographic agility".
            //
            // This is similar in practice to PKCS#7 messaging, but this uses a
            // private-scoped byte rather than a public-scoped Object IDentifier (OID).
            // Please note that the scheme in this example adheres to no particular
            // standard, and is unlikely to survive to a more complete implementation in
            // the .NET Framework.
            //
            // You may be well-served by prepending a version number byte to this
            // message, but may want to avoid the value 0x30 (the leading byte value for
            // DER-encoded structures such as X.509 certificates and PKCS#7 messages).
            byte[] algorithmChoices = { (byte)aeCipher, (byte)aeMac };
            byte[] iv;
            byte[] cipherText;
            byte[] tag;

            // Using our algorithm choices, open an HMAC (as an authentication tag
            // generator) and a SymmetricAlgorithm which use different keys each derived
            // from the same master key.
            //
            // A custom implementation may very well have distinctly managed secret keys
            // for the MAC and cipher, this example merely demonstrates the master to
            // derived key methodology to encourage key separation from the MAC and
            // cipher keys.
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
                using (ICryptoTransform encryptor = cipher.CreateEncryptor())
                {
                    // Since no IV was provided, a random one has been generated
                    // during the call to CreateEncryptor.
                    //
                    // But note that it only does the auto-generation once. If the cipher
                    // object were used again, a call to GenerateIV would have been
                    // required.
                    iv = cipher.IV;

                    cipherText = Transform(encryptor, message, 0, message.Length);
                }

                // The IV and ciphertest both need to be included in the MAC to prevent
                // tampering.
                //
                // By including the algorithm identifiers, we have technically moved from
                // simple Authenticated Encryption (AE) to Authenticated Encryption with
                // Additional Data (AEAD). By including the algorithm identifiers in the
                // MAC, it becomes harder for an attacker to change them as an attempt to
                // perform a downgrade attack.
                //
                // If you've added a data format version field, it can also be included
                // in the MAC to further inhibit an attacker's options for confusing the
                // data processor into believing the tampered message is valid.
                tagGenerator.AppendData(algorithmChoices);
                tagGenerator.AppendData(iv);
                tagGenerator.AppendData(cipherText);
                tag = tagGenerator.GetHashAndReset();
            }

            // Build the final result as the concatenation of everything except the keys.
            int totalLength =
                algorithmChoices.Length +
                tag.Length +
                iv.Length +
                cipherText.Length;

            byte[] output = new byte[totalLength];
            int outputOffset = 0;

            Append(algorithmChoices, output, ref outputOffset);
            Append(tag, output, ref outputOffset);
            Append(iv, output, ref outputOffset);
            Append(cipherText, output, ref outputOffset);

            Debug.Assert(outputOffset == output.Length);
            return output;
        }

        /// <summary>
        /// Reads a message produced by <see cref="Encrypt"/> after verifying it hasn't
        /// been tampered with.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="cipherText">
        /// The output of <see cref="Encrypt"/>: a concatenation of a cipher ID, mac ID,
        /// authTag, IV, and cipherText.
        /// </param>
        /// <returns>The decrypted content.</returns>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="masterKey"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="cipherText"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="CryptographicException">
        /// <paramref name="cipherText"/> identifies unknown algorithms, is not long
        /// enough, fails a data integrity check, or fails to decrypt.
        /// </exception>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or larger) value
        /// generated by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>. This implementation chooses to
        /// block deficient inputs by length, but doesn't make any attempt at
        /// discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase),
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Decrypt(byte[] masterKey, byte[] cipherText)
        {
            // This example continues the .NET practice of throwing exceptions for
            // failures. If you consider message tampering to be normal (and thus
            // "not exceptional") behavior, you may like the signature
            // bool Decrypt(byte[] messageKey, byte[] cipherText, out byte[] message)
            // better.
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (cipherText == null)
                throw new ArgumentNullException(nameof(cipherText));

            // The format of this message is assumed to be public, so there's no harm in
            // saying ahead of time that the message makes no sense.
            if (cipherText.Length < 2)
            {
                throw new CryptographicException();
            }

            // Use the message algorithm headers to determine what cipher algorithm and
            // MAC algorithm are going to be used. Since the same Key Derivation
            // Functions (KDFs) are being used in Decrypt as Encrypt, the keys are also
            // the same.
            AeCipher aeCipher = (AeCipher)cipherText[0];
            AeMac aeMac = (AeMac)cipherText[1];

            using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                int blockSizeInBytes = cipher.BlockSize / 8;
                int tagSizeInBytes = tagGenerator.HashSize / 8;
                int headerSizeInBytes = 2;
                int tagOffset = headerSizeInBytes;
                int ivOffset = tagOffset + tagSizeInBytes;
                int cipherTextOffset = ivOffset + blockSizeInBytes;
                int cipherTextLength = cipherText.Length - cipherTextOffset;
                int minLen = cipherTextOffset + blockSizeInBytes;

                // Again, the minimum length is still assumed to be public knowledge,
                // nothing has leaked out yet. The minimum length couldn't just be calculated
                // without reading the header.
                if (cipherText.Length < minLen)
                {
                    throw new CryptographicException();
                }

                // It's very important that the MAC be calculated and verified before
                // proceeding to decrypt the ciphertext, as this prevents any sort of
                // information leaking out to an attacker.
                //
                // Don't include the tag in the calculation, though.

                // First, everything before the tag (the cipher and MAC algorithm ids)
                tagGenerator.AppendData(cipherText, 0, tagOffset);

                // Skip the data before the tag and the tag, then read everything that
                // remains.
                tagGenerator.AppendData(
                    cipherText,
                    tagOffset + tagSizeInBytes,
                    cipherText.Length - tagSizeInBytes - tagOffset);

                byte[] generatedTag = tagGenerator.GetHashAndReset();

                // The time it took to get to this point has so far been a function only
                // of the length of the data, or of non-encrypted values (e.g. it could
                // take longer to prepare the *key* for the HMACSHA384 MAC than the
                // HMACSHA256 MAC, but the algorithm choice wasn't a secret).
                //
                // If the verification of the authentication tag aborts as soon as a
                // difference is found in the byte arrays then your program may be
                // acting as a timing oracle which helps an attacker to brute-force the
                // right answer for the MAC. So, it's very important that every possible
                // "no" (2^256-1 of them for HMACSHA256) be evaluated in as close to the
                // same amount of time as possible. For this, we call CryptographicEquals
                if (!CryptographicEquals(
                    generatedTag,
                    0,
                    cipherText,
                    tagOffset,
                    tagSizeInBytes))
                {
                    // Assuming every tampered message (of the same length) took the same
                    // amount of time to process, we can now safely say
                    // "this data makes no sense" without giving anything away.
                    throw new CryptographicException();
                }

                // Restore the IV into the symmetricAlgorithm instance.
                byte[] iv = new byte[blockSizeInBytes];
                Buffer.BlockCopy(cipherText, ivOffset, iv, 0, iv.Length);
                cipher.IV = iv;

                using (ICryptoTransform decryptor = cipher.CreateDecryptor())
                {
                    return Transform(
                        decryptor,
                        cipherText,
                        cipherTextOffset,
                        cipherTextLength);
                }
            }
        }

        private static byte[] Transform(
            ICryptoTransform transform,
            byte[] input,
            int inputOffset,
            int inputLength)
        {
            // Many of the implementations of ICryptoTransform report true for
            // CanTransformMultipleBlocks, and when the entire message is available in
            // one shot this saves on the allocation of the CryptoStream and the
            // intermediate structures it needs to properly chunk the message into blocks
            // (since the underlying stream won't always return the number of bytes
            // needed).
            if (transform.CanTransformMultipleBlocks)
            {
                return transform.TransformFinalBlock(input, inputOffset, inputLength);
            }

            // If our transform couldn't do multiple blocks at once, let CryptoStream
            // handle the chunking.
            using (MemoryStream messageStream = new MemoryStream())
            using (CryptoStream cryptoStream =
                new CryptoStream(messageStream, transform, CryptoStreamMode.Write))
            {
                cryptoStream.Write(input, inputOffset, inputLength);
                cryptoStream.FlushFinalBlock();
                return messageStream.ToArray();
            }
        }

        /// <summary>
        /// Open a properly configured <see cref="SymmetricAlgorithm"/> conforming to the
        /// scheme identified by <paramref name="aeCipher"/>.
        /// </summary>
        /// <param name="aeCipher">The cipher mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// A SymmetricAlgorithm object with the right key, cipher mode, and padding
        /// mode; or <c>null</c> on unknown algorithms.
        /// </returns>
        private static SymmetricAlgorithm GetCipher(AeCipher aeCipher, byte[] masterKey)
        {
            SymmetricAlgorithm symmetricAlgorithm;

            switch (aeCipher)
            {
                case AeCipher.Aes256CbcPkcs7:
                    symmetricAlgorithm = Aes.Create();
                    // While 256-bit, CBC, and PKCS7 are all the default values for these
                    // properties, being explicit helps comprehension more than it hurts
                    // performance.
                    symmetricAlgorithm.KeySize = 256;
                    symmetricAlgorithm.Mode = CipherMode.CBC;
                    symmetricAlgorithm.Padding = PaddingMode.PKCS7;
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            //
            // Since none of the symmetric encryption algorithms currently in .NET
            // support key sizes greater than 256-bit, we can use HMACSHA256 with
            // NIST SP 800-108 5.1 (Counter Mode KDF) to derive a value that is
            // no smaller than the key size, then Array.Resize to trim it down as
            // needed.

            using (HMAC hmac = new HMACSHA256(masterKey))
            {
                // i=1, Label=ASCII(cipher)
                byte[] cipherKey = hmac.ComputeHash(
                    new byte[] { 1, 99, 105, 112, 104, 101, 114 });

                // Resize the array to the desired keysize. KeySize is in bits,
                // and Array.Resize wants the length in bytes.
                Array.Resize(ref cipherKey, symmetricAlgorithm.KeySize / 8);

                symmetricAlgorithm.Key = cipherKey;
            }

            return symmetricAlgorithm;
        }

        /// <summary>
        /// Open a properly configured <see cref="HMAC"/> conforming to the scheme
        /// identified by <paramref name="aeMac"/>.
        /// </summary>
        /// <param name="aeMac">The message authentication mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// An HMAC object with the proper key, or <c>null</c> on unknown algorithms.
        /// </returns>
        private static HMAC GetMac(AeMac aeMac, byte[] masterKey)
        {
            HMAC hmac;

            switch (aeMac)
            {
                case AeMac.HMACSHA256:
                    hmac = new HMACSHA256();
                    break;
                case AeMac.HMACSHA384:
                    hmac = new HMACSHA384();
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            // Since the output size of the HMAC is the same as the ideal key size for
            // the HMAC, we can use the master key over a fixed input once to perform
            // NIST SP 800-108 5.1 (Counter Mode KDF):
            hmac.Key = masterKey;

            // i=1, Context=ASCII(MAC)
            byte[] newKey = hmac.ComputeHash(new byte[] { 1, 77, 65, 67 });

            hmac.Key = newKey;
            return hmac;
        }

        // A simple helper method to ensure that the offset (writePos) always moves
        // forward with new data.
        private static void Append(byte[] newData, byte[] combinedData, ref int writePos)
        {
            Buffer.BlockCopy(newData, 0, combinedData, writePos, newData.Length);
            writePos += newData.Length;
        }

        /// <summary>
        /// Compare the contents of two arrays in an amount of time which is only
        /// dependent on <paramref name="length"/>.
        /// </summary>
        /// <param name="a">An array to compare to <paramref name="b"/>.</param>
        /// <param name="aOffset">
        /// The starting position within <paramref name="a"/> for comparison.
        /// </param>
        /// <param name="b">An array to compare to <paramref name="a"/>.</param>
        /// <param name="bOffset">
        /// The starting position within <paramref name="b"/> for comparison.
        /// </param>
        /// <param name="length">
        /// The number of bytes to compare between <paramref name="a"/> and
        /// <paramref name="b"/>.</param>
        /// <returns>
        /// <c>true</c> if both <paramref name="a"/> and <paramref name="b"/> have
        /// sufficient length for the comparison and all of the applicable values are the
        /// same in both arrays; <c>false</c> otherwise.
        /// </returns>
        /// <remarks>
        /// An "insufficient data" <c>false</c> response can happen early, but otherwise
        /// a <c>true</c> or <c>false</c> response take the same amount of time.
        /// </remarks>
        [MethodImpl(MethodImplOptions.NoInlining | MethodImplOptions.NoOptimization)]
        private static bool CryptographicEquals(
            byte[] a,
            int aOffset,
            byte[] b,
            int bOffset,
            int length)
        {
            Debug.Assert(a != null);
            Debug.Assert(b != null);
            Debug.Assert(length >= 0);

            int result = 0;

            if (a.Length - aOffset < length || b.Length - bOffset < length)
            {
                return false;
            }

            unchecked
            {
                for (int i = 0; i < length; i++)
                {
                    // Bitwise-OR of subtraction has been found to have the most
                    // stable execution time.
                    //
                    // This cannot overflow because bytes are 1 byte in length, and
                    // result is 4 bytes.
                    // The OR propagates all set bytes, so the differences are only
                    // present in the lowest byte.
                    result = result | (a[i + aOffset] - b[i + bOffset]);
                }
            }

            return result == 0;
        }
    }
}
```
