---
title: Уязвимость расшифровки CBC
description: Узнайте, как обнаруживать и устранять временные уязвимости с помощью симметричной расшифровки в режиме Cipher-Block-chaining (CBC) с использованием заполнения.
ms.date: 06/12/2018
author: blowdart
ms.author: mairaw
ms.openlocfilehash: 1d570cf3da197e7af5c1a1ab4e4df0d21f2cb2d7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347234"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a>Уязвимости в учете времени при симметричной расшифровке в режиме CBC с использованием заполнения

Корпорация Майкрософт считает, что больше не рекомендуется расшифровывать данные, зашифрованные с помощью режима Cipher-Block-chaining (CBC) симметричного шифрования, если для проверяемого дополнения применяется без предварительного обеспечения целостности зашифрованного текста, за исключением очень специфичных обстоятельствах. Эта выработка основана на текущих результатах криптографических исследований. 

## <a name="introduction"></a>Введение

Заполнение Oracle — это тип атаки на зашифрованные данные, позволяющий злоумышленнику расшифровать содержимое данных без знания ключа.

Oracle ссылается на "сообщить", который предоставляет злоумышленнику сведения о том, правильно ли выполняется действие. Представьте себе игру с доской или картой с дочерним. Когда его поверхность высветится большой улыбкой, так как она считает, что она собирается выполнить хорошее перемещение, это будет Oracle. Вы, как соперник, можете использовать эту Oracle для планирования следующего перемещения соответствующим образом.

Заполнение — это конкретный криптографический термин. Некоторые шифры, которые используются для шифрования данных, работают с блоками данных, в которых каждый блок имеет фиксированный размер. Если данные, которые нужно зашифровать, имеют неправильный размер для заполнения блоков, данные будут заполнены до тех пор, пока они не будут заполнены. Для многих видов заполнения требуется, чтобы заполнение всегда присутствовало, даже если исходные данные имеют правильный размер. Это позволяет всегда безопасно удалять заполнение после расшифровки.

Поместив две вещи вместе, реализация программного обеспечения с заполнением Oracle показывает, являются ли расшифрованные данные допустимыми заполнениями. Oracle может быть так же простым, как возврат значения, говорящего «Недопустимое заполнение», или что-то более сложное, например получение значительно улучшает другого времени для обработки допустимого блока, а не недопустимого блока.

Блочные шифры имеют другое свойство, называемое режимом, которое определяет связь данных в первом блоке с данными во втором блоке и т. д. Одним из наиболее часто используемых режимов является CBC. CBC вводит исходный случайный блок, известный как вектор инициализации (IV), и объединяет предыдущий блок с результатом статического шифрования, чтобы сделать так, чтобы шифрование того же сообщения с одним и тем же ключом не всегда выводило одинаковые зашифрованные выходные данные.

Злоумышленник может использовать заполнение Oracle, в сочетании с тем, как структурированы данные CBC, отправлять слегка измененные сообщения в код, предоставляющий доступ к Oracle, и выполнять отправку данных до тех пор, пока Oracle не сообщит, что данные верны. Из этого ответа злоумышленник может расшифровать байт сообщения по байтам.

Современные компьютерные сети имеют такое высокое качество, что злоумышленник может обнаружить очень малые (менее 0,1 мс) различия во времени выполнения на удаленных системах. Приложения, в которых предполагается Успешная расшифровка, могут быть уязвимы, только если данные не были изменены с помощью средств, предназначенных для отслеживания различий в успешной и неудачной расшифровке. Хотя это различие может быть более значительным в некоторых языках или библиотеках, а не в других, теперь считается, что это практическая угроза для всех языков и библиотек, когда учитывается ответ приложения на отказ.

Эта атака зависит от возможности изменения зашифрованных данных и проверки результата с помощью Oracle. Единственным способом устранения атаки является обнаружение изменений в зашифрованных данных и отказ от выполнения каких-либо действий с ним. Стандартный способ сделать это — создать подпись для данных и проверить подпись перед выполнением каких-либо операций. Подпись должна быть проверяемой, она не может быть создана злоумышленником, в противном случае она изменит зашифрованные данные, а затем вычислит новую подпись на основе измененных данных. Один распространенный тип соответствующей сигнатуры называется кодом проверки подлинности сообщения с ключом (HMAC). Код HMAC отличается от контрольной суммы тем, что он принимает секретный ключ, известный только пользователю, создающему HMAC, и пользователю, который его проверяет. Без ключа вы не сможете создать правильный код HMAC. При получении данных вы получите зашифрованные данные, независимо Вычислите код HMAC с помощью секретного ключа и общего ресурса отправителя, а затем сравните код HMAC, отправленный на тот, который вы вычислите. Это сравнение должно быть постоянным. в противном случае вы добавили еще одну обнаруживаемую версию Oracle, что позволяет использовать другой тип атаки.

В целом, чтобы безопасно использовать блочные шифры CBC, их необходимо объединить с HMAC (или другой проверкой целостности данных), которую вы проверите с помощью сравнения постоянного времени перед попыткой расшифровки данных. Так как все измененные сообщения принимают одинаковое время для получения ответа, атака предотвращается.

## <a name="who-is-vulnerable"></a>Кто уязвим

Эта уязвимость относится как к управляемым, так и к собственным приложениям, выполняющим шифрование и расшифровку. К ним относятся, например:

- Приложение, которое шифрует файл cookie для последующей расшифровки на сервере.
- Приложение базы данных, предоставляющее пользователям возможность вставлять данные в таблицу, столбцы которой затем расшифровываются.
- Приложение передачи данных, основанное на шифровании с использованием общего ключа для защиты передаваемых данных.
- Приложение, которое шифрует и расшифровывает сообщения "внутри" туннеля TLS.

Обратите внимание, что использование только протокола TLS может не защищать вас в этих сценариях.

Уязвимое приложение:

- Расшифровывает данные с помощью режима шифра CBC с проверяемым режимом заполнения, например PKCS # 7 или ANSI X. 923.
- Выполняет расшифровку без выполнения проверки целостности данных (с помощью MAC или асимметричной цифровой подписи).

Это также относится к приложениям, созданным на основе абстракций поверх этих примитивов, например синтаксиса криптографических сообщений (PKCS # 7/CMS) Енвелопеддата Structure.

## <a name="related-areas-of-concern"></a>Связанные области

Исследования привели к тому, что корпорация Майкрософт позаботится о сообщениях CBC, дополненных заполнением ISO 10126, если сообщение имеет хорошо известную или прогнозируемую структуру нижнего колонтитула. Например, содержимое, подготовленное согласно правилам синтаксиса W3C по шифрованию XML и рекомендациям по обработке (ксмленк, EncryptedXml). Хотя рекомендации консорциума W3C по подписанию сообщения, в то же время, были признаны допустимыми, корпорация Майкрософт рекомендует всегда выполнять шифрование-then-Sign.

Разработчикам приложений всегда следует учитывать проверку применимости асимметричного ключа подписи, так как нет встроенных отношений доверия между асимметричным ключом и произвольным сообщением.

## <a name="details"></a>Подробности

Исторически существует согласие на то, что важно как шифровать, так и проверять подлинность важных данных, используя такие средства, как подписи HMAC или RSA. Однако были менее четкие рекомендации по последовательности операций шифрования и проверки подлинности. Из-за уязвимости, описанной в этой статье, руководство Майкрософт теперь всегда использует парадигму "шифрования и подписи". То есть сначала зашифровать данные с помощью симметричного ключа, а затем вычислить MAC-или асимметричную подпись по зашифрованным данным (зашифрованные данные). При расшифровке данных выполните обратную. Сначала подтвердите MAC или подпись зашифрованного текста, а затем расшифровать его.

В течение 10 лет известно, что класс уязвимостей, известных как «атаки Oracle с заполнением», уже существует. Эти уязвимости позволяют злоумышленнику расшифровывать данные, зашифрованные симметричными блочными алгоритмами, такими как AES и 3DES, используя не более 4096 попыток на блок данных. Эти уязвимости позволяют использовать тот факт, что блочные шифры чаще всего используются с проверяемыми данными заполнения в конце. Было обнаружено, что если злоумышленник может изменить зашифрованный текст и выяснить, привело ли искажение к ошибке в формате заполнения в конце, злоумышленник может расшифровать данные.

Изначально атаки на практике были основаны на службах, которые возвращали различные коды ошибок в зависимости от того, является ли заполнение допустимым, например ASP.NET уязвимость [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070). Однако теперь корпорация Майкрософт считает, что разумно выполнять аналогичные атаки, используя только различия между обработкой допустимых и недопустимых дополнений.

При условии, что схема шифрования использует сигнатуру и проверка сигнатуры выполняется с помощью фиксированной среды выполнения для заданной длины данных (независимо от содержимого), целостность данных может быть проверена без передачи каких-либо сведений злоумышленнику через канал на [стороне](https://en.wikipedia.org/wiki/Side-channel_attack). Так как проверка целостности отклоняет любые неизмененные сообщения, угроза заполнения Oracle уменьшается.

## <a name="guidance"></a>Руководство

Прежде всего, корпорация Майкрософт рекомендует, чтобы все данные, имеющие конфиденциальность, передавались по протоколу TLS, последователем на SSL (SSL).

Затем проанализируйте приложение следующим образом:

- Точное понимание того, какое шифрование вы используете, и какое шифрование предоставляется платформами и API-интерфейсами, которые вы используете.
- Убедитесь, что каждое использование на каждом уровне [алгоритма симметричного блочного шифрования](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), такого как AES и 3DES, в режиме CBC включает использование проверки целостности данных с ключом секрета (асимметричная сигнатура, HMAC или переключение режима шифрования в режим с [проверкой подлинности](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE), например gcm или CCM).

В соответствии с текущими исследованиями, как правило, предполагается, что если шаги проверки подлинности и шифрования выполняются независимо для режимов шифрования, не относящихся к AE, то лучшим вариантом является проверка подлинности зашифрованного текста (Encrypt-then-Sign). Тем не менее, один и тот же правильный ответ на криптографию не подходит, и это обобщение не так хорошо, как направленные советы от профессионального криптограф.

Приложения, которые не могут изменить свой формат обмена сообщениями, но выполняют расшифровку CBC без проверки подлинности, рекомендуется попытаться включить такие способы защиты, как:

- Расшифровать без разрешения на расшифровку или удаление заполнения:
  - Все примененное заполнение все еще необходимо удалить или проигнорировать, вы перемещаете нагрузку в приложение.
  - Преимущество заключается в том, что проверка заполнения и удаление могут быть включены в другую логику проверки данных приложения. Если проверка заполнения и проверка данных могут выполняться за постоянное время, угроза сокращается.
  - Поскольку при интерпретации заполнения изменяется длина воспринимаемого сообщения, все равно могут быть получены сведения о времени, выдаваемые этим подходом.
- Измените режим заполнения отступа на ISO10126:
  - Дополнение ISO10126 расшифровки совместимо с заполнением и заполнением шифрования PKCS7 и ANSIX923.
  - Изменение режима позволяет сократить заполнение базы данных Oracle до 1 байта вместо всего блока. Однако если содержимое имеет хорошо известный нижний колонтитул, например закрывающий XML-элемент, связанные атаки могут продолжать атакуть остальную часть сообщения.
  - Это также не предотвращает восстановление в виде открытого текста в ситуациях, когда злоумышленник может присвоить тот же открытый текст для шифрования несколько раз с другим смещением сообщения.
- Вызовите оценку вызова расшифровки для ослабления сигнала синхронизации:
  - Вычисление времени удержания должно быть минимальным, чем максимальное количество времени, которое будет выполнено операцией расшифровки для любого сегмента данных, содержащего заполнение.
  - Вычисления времени должны выполняться в соответствии с рекомендациями по получению [меток времени с высоким разрешением](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps), а не с помощью <xref:System.Environment.TickCount?displayProperty=nameWithType> (подключается или переполнение) или вычитанием двух системных меток времени (в соответствии с ошибками корректировки NTP).
  - Вычисления времени должны быть включительно операции расшифровки, включая все возможные исключения в управляемых приложениях или C++ приложения, а не только в конце.
  - Если успех или неудача было определено, то в течение срока действия шлюза времени необходимо возвращать ошибку.
- Службы, выполняющие расшифровку без проверки подлинности, должны иметь наблюдение на месте, чтобы обнаружить переполнение сообщений "недопустимо".
  - Имейте в виду, что этот сигнал несет как ложные срабатывания (данные с легальным повреждением), так и ложные отрицательные (в результате атаки достаточно долгого времени на обнаружение избегать обнаружения).

## <a name="finding-vulnerable-code---native-applications"></a>Поиск уязвимого кода — собственные приложения

Для программ, созданных на основе библиотеки Windows Cryptography: следующего поколения (CNG):

- Вызов расшифровки — это [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), указывающий флаг `BCRYPT_BLOCK_PADDING`.
- Маркер ключа был инициализирован путем вызова [бкриптсетпроперти](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) с параметром [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) , для которого задано значение `BCRYPT_CHAIN_MODE_CBC`.
  - Поскольку `BCRYPT_CHAIN_MODE_CBC` является значением по умолчанию, затронутый код может не иметь никаких значений для `BCRYPT_CHAINING_MODE`.

Для программ, созданных на основе старого API шифрования Windows:

- Вызов расшифровки заключается в [криптдекрипт](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) с `Final=TRUE`.
- Маркер ключа был инициализирован путем вызова [криптсеткэйпарам](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) с параметром [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) , для которого задано значение `CRYPT_MODE_CBC`.
  - Поскольку `CRYPT_MODE_CBC` является значением по умолчанию, затронутый код может не иметь никаких значений для `KP_MODE`.

## <a name="finding-vulnerable-code---managed-applications"></a>Поиск уязвимых приложений, управляемых кодом

- Вызов расшифровки относится к методам <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> или <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> в <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.
  - Сюда входят следующие производные типы в .NET, но могут также включать сторонние типы:
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
- Свойству <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> присвоено значение <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>или <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.
  - Поскольку <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> является значением по умолчанию, затронутый код может никогда не присваивать свойству <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType>.
- Свойству <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> присвоено значение <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>
  - Поскольку <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> является значением по умолчанию, затронутый код может никогда не присваивать свойству <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType>.

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a>Поиск уязвимого кода — синтаксис криптографического сообщения

Сообщение CMS Енвелопеддата без проверки подлинности, зашифрованное содержимое которого использует режим CBC AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) или RC2 (1.2.840.113549.3.2). уязвимые, а также сообщения, использующие любые другие алгоритмы блочного шифра в режиме CBC.

Хотя потоковые шифры не подвержены этой конкретной уязвимости, корпорация Майкрософт рекомендует всегда проверять подлинность данных при проверке значения Контентенкриптионалгорисм.

Для управляемых приложений в качестве любого значения, передаваемого в <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>, можно обнаружить большой двоичный объект CMS Енвелопеддата.

Для собственных приложений можно обнаружить большой двоичный объект Енвелопеддата CMS в виде любого значения, предоставленного для обработчика CMS через [криптмсгупдате](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) , получившийся [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) `CMSG_ENVELOPED` и/или обработчик CMS отправляет инструкцию `CMSG_CTRL_DECRYPT` через [криптмсгконтрол](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).

## <a name="vulnerable-code-example---managed"></a>Пример уязвимого кода — управляемый

Этот метод считывает файл cookie и расшифровывает его, и проверка целостности данных не видна. Таким образом, содержимое файла cookie, считываемого этим методом, может быть атаковано пользователем, получившим его, или злоумышленником, получившим зашифрованное значение файла cookie.

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

## <a name="example-code-following-recommended-practices---managed"></a>Пример кода ниже рекомендованных методов управления

В следующем примере кода используется нестандартный формат сообщений

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

где идентификаторы алгоритмов `cipher_algorithm_id` и `hmac_algorithm_id` являются локальными (не стандартными) представлениями этих алгоритмов. Эти идентификаторы могут иметь смысл в других частях существующего протокола обмена сообщениями, а не в качестве исходного сцепленного ByteStream.

В этом примере также используется один главный ключ для получения ключа шифрования и ключа HMAC. Это предоставляется и для того, чтобы превратить приложение с несколькими ключами в приложение с двойным ключом, а также обеспечить хранение двух ключей в качестве различных значений. Он дополнительно гарантирует, что ключ HMAC и ключ шифрования не могут быть синхронизированы.

Этот пример не принимает <xref:System.IO.Stream> для шифрования или расшифровки. Текущий формат данных затрудняет однопроходный шифрование, так как `hmac_tag` значение предшествует зашифрованному тексту. Однако этот формат был выбран, так как он сохраняет все элементы фиксированного размера в начале, чтобы упростить синтаксический анализ. При использовании этого формата данных возможна однопроходная расшифровка, хотя разработчику необходимо вызвать Жесашандресет и проверить результат перед вызовом TransformFinalBlock. Если шифрование потоковой передачи имеет важное значение, может потребоваться другой режим СЗ.

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
