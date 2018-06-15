---
title: Время уязвимостей и режим CBC Симметричная расшифровка с помощью заполнения
description: Дополнительные сведения о обнаруживать и устранять уязвимости времени расшифровка симметричного режим сцепления блоков шифра (CBC), с помощью заполнения.
ms.date: 06/12/2018
author: blowdart
ms.author: mairaw
ms.openlocfilehash: a07acbb943c430f6e26bec44f55a5c84306da513
ms.sourcegitcommit: 73a662360bbe2f43c19aca1fbcc2565025c60cd8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2018
ms.locfileid: "35327461"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a>Время уязвимостей и режим CBC Симметричная расшифровка с помощью заполнения

Корпорации Майкрософт, в зависимости от известные криптографических исследований, полагает, что, за исключением особых ситуациях, он больше не безопасно расшифровывать данные, зашифрованные с помощью симметричного шифрования режим сцепления блоков шифра (CBC), после заполнения проверяемый применить без убедитесь, что целостность зашифрованных данных.

## <a name="introduction"></a>Вступление

Атаке заполнения oracle — это тип атаки зашифрованные данные, которые позволяет злоумышленнику расшифровать содержимое данных, не зная ключа.

Oracle ссылается «сообщить» которых дает злоумышленнику информацию о ли действие, которое они исполняется указано правильно, или нет. Представьте себе воспроизведение доску или карт игры с дочерним. При ее начертания светиться с большой одобрение, так как она полагает, что она является об для хорошей перемещения, которая является oracle. Как игрок, можно использовать этот oracle для планирования и переместить далее соответствующим образом.

Заполнение составляет определенный термин шифрования. Некоторые шифров, которые являются алгоритмы, используемые для шифрования данных, работать на блоки данных, где каждый блок имеет фиксированный размер. Если данные, которые требуется зашифровать не самый подходящий размер для заполнения блоков, данные дополняются до ее. Множество форм заполнения требуют этого дополнения, чтобы всегда присутствовать, даже если исходная входная последовательность была неправильный размер. Это позволяет дополнения, чтобы всегда безопасно удалить при расшифровке.

Совместное размещение две вещи, реализации программы с oracle заполнения показывает, имеет ли расшифрованные данные допустимым заполнения. Oracle может быть что-то сложнее, чем возврат значения с сообщением «Недопустимый заполнение» или более сложное подобный значительно другое время для обработки является допустимым блоком, в отличие от недопустимый блок.

Блочных шифров другое свойство, которое называется режим, который определяет связь данных в первый блок данных во втором блоке, и так далее. Одним из наиболее распространенных режимов является CBC. CBC представляет начальное случайное блокировать, известные как вектор инициализации (IV) и объединяет предыдущего блока с результатом статического шифрования, чтобы сделать его таким образом, шифрование и то же сообщение с тем же ключом не всегда позволяет создавать такие же выходные данные зашифрованных.

Злоумышленник может использовать заполнение oracle, в сочетании с структуру данных CBC, для отправки сообщений слегка измененный код, который предоставляет oracle и сохранить отправка данных, пока oracle уведомляющее правильности данных. Из этого ответа злоумышленник может расшифровать сообщение байт за байтом.

Современные персональные компьютеры сети имеют такие высокого качества, злоумышленник может обнаружить очень мало (менее 0,1 мс), время различия в удаленных системах. Приложения, при условии что успешной расшифровки может произойти только в том случае, если данные не подделаны может быть подвержен атакам с помощью средств, предназначенных для наблюдения за различия в успешные и неудачные расшифровки. Хотя эта разница времени может быть более значительные на некоторых языках или библиотеки, чем другие, теперь полагается, это практические угроз для всех языков и библиотек, когда учитывается ответ сбой приложения.

Возможность изменить зашифрованные данные и проверить результаты с oracle использует такой атаки. Единственным способом, полностью защититься от атак является обнаруживать изменения зашифрованные данные и не будет выполнять каких-либо действий с ним. Это стандартный способ сделать это является создание подпись для данных и проверка подписи перед любой операции выполняются. Подпись должна поддаваться, не может быть создан злоумышленником, в противном случае они бы изменить зашифрованные данные, а затем вычисления используется новая подпись, на основе измененных данных. Один общий тип с соответствующей сигнатурой называется кода проверки подлинности сообщения хэширования с ключом (HMAC). Код HMAC отличается от контрольной суммы, что он принимает секретный ключ, известный только пользователю, формирующего HMAC и проверки его пользователю. Даже при отсутствии ключа не могут производить правильный HMAC. При получении данных, следует воспользоваться зашифрованные данные, независимо друг от друга вычислений с помощью секретного ключа HMAC вы отправителя общей папки, а затем сравнить вычисляемые HMAC, они отправлены по одному. Это сравнение должно быть константой времени, в противном случае вы добавили другой выявить oracle, позволяя другой тип атаки.

Таким образом использование дополняются блочные шифры CBC безопасно, необходимо объединить их с HMAC (или другой проверки целостности данных), можно проверить с помощью сравнения константном времени, прежде чем для расшифровки данных. Поскольку все сообщения измененную принимать то же время сумма для получения ответа, не будет атаки.

## <a name="who-is-vulnerable"></a>Кто является уязвимым

Эта уязвимость существует управляемый и машинный приложения, которое выполняет свои собственные шифрования и расшифровки. Сюда входят, например:

- Приложение, которое шифрует файл cookie для расшифровки более поздней версии на сервере.
- Приложение базы данных, которое предоставляет возможности для пользователей, для вставки данных в таблицу, столбцы которых затем расшифрованы лицом.
- Приложения, основанные на шифрование с использованием общего ключа для защиты передачи данных для передачи данных.
- Приложения, который шифрует и расшифровывает сообщения TLS-туннеля «внутри».

Обратите внимание, что использование TLS сама по себе может защитит вас в этих сценариях.

Уязвимого приложения:

- Расшифровывает данные с помощью шифра CBC режим с режимом заполнения проверяемый, например PKCS #7 или ANSI X.923.
- Выполняет расшифровку без выполнять проверку целостности данных (через MAC или асимметричный цифровой подписи).

Это также относится к приложениям, построена на базе абстракции поверх этих примитивах, например структуру EnvelopedData Cryptographic Message Syntax (PKCS #7/CMS).

## <a name="related-areas-of-concern"></a>Связанные проблемные области.

Справочные материалы привело Майкрософт для дальнейшего занимается CBC сообщений, которые заполняются ISO 10126-эквивалент внутренних полей при сообщении имеет структуру, хорошо известных и прогнозируемых нижний колонтитул. Например содержимое, подготовленных в соответствии с правилами синтаксиса шифрования XML консорциума W3C и рекомендации по обработке (xmlenc EncryptedXml). Хотя рекомендации W3C подписал сообщение, а затем зашифровать считается соответствующее во время, теперь рекомендуется всегда делаем шифрование then подписью.

Разработчики приложений должны всегда учитывать проверка применимости асимметричный ключ подписи, как не задано отношение доверия, присущие между асимметричного ключа и случайное сообщение.

## <a name="details"></a>Подробные сведения

Исторически произошел согласие, очень важно для шифрования и проверки подлинности с помощью средств подписи HMAC или RSA важных данных. Однако было меньше четкие инструкции о том, как последовательность операций шифрования и проверки подлинности. Из-за уязвимости, описанные в этой статье рекомендации корпорации Майкрософт — теперь всегда использовать парадигма «шифрование then подписью». То есть сначала шифрование данных с помощью симметричного ключа, а затем вычислений MAC или асимметричной подписи над зашифрованного текста (зашифрованных данных). При расшифровке данных, выполните обратное. Во-первых Подтвердите MAC или подписи зашифрованного текста, а затем расшифровать его.

Класс уязвимостей, известные как «padding атак oracle» известно, что существует более 10 лет. Эти уязвимости злоумышленник может расшифровать данные, зашифрованные блок симметричные алгоритмы, например AES и 3DES, используя не более 4096 попыток каждого блока данных. Сделать эти уязвимости использование тот факт, что блок шифры чаще всего используются с данными проверяемый заполнения в конце. Найден, что если злоумышленник может незаконно зашифрованных данных и выяснить ли изменение данных вызвала ошибку в формате заполнения в конце, злоумышленник может расшифровать данные.

Изначально практические атак были основаны на службы, которые будут возвращать различные коды ошибок зависимости от того, было ли заполнение правильной, например уязвимость ASP.NET [MS10-070](https://technet.microsoft.com/library/security/ms10-070.aspx). Тем не менее Корпорация Майкрософт теперь считает, что это целесообразно провести аналогичные атак с использованием только различия по синхронизации между обработки допустимые и недопустимые заполнения.

Если подпись использует схему шифрования, а, проверка подписи выполняется с предопределенной среды выполнения для данной длины данных (независимо от содержимого), без передачи сведений, можно проверить целостность данных Злоумышленник через [канала со стороны](https://en.wikipedia.org/wiki/Side-channel_attack). Поскольку проверка целостности отклоняет все измененные сообщения, угроза oracle заполнения устраняется.

## <a name="guidance"></a>Руководство

Первое и самое главное Корпорация Майкрософт рекомендует, что все данные, имеющие конфиденциальность должен передаваться через Transport Layer Security (TLS), преемник для Secure Sockets Layer (SSL).

Далее проанализируйте приложение:

- Понять, какие шифрование, выполняемой и точно какие Шифрование обеспечивается корпорацией платформ и API, вы используете.
- Быть что каждого использования на каждом уровне симметричный [алгоритм шифрования блока](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), таких как AES и 3DES, в режиме CBC включить использование проверку целостности данных с закрытым ключом (асимметричной подписи HMAC или изменить режим шифрования для [шифрования с проверкой подлинности](https://en.wikipedia.org/wiki/Authenticated_encryption) режим (AE), например GCM или CCM).

На основании текущего research, обычно считается, если действия проверки подлинности и шифрования выполняются независимо друг от друга не AE режимов шифрования, проверки подлинности зашифрованного текста (шифрование, затем знак) вариант является наилучшим Общие. Однако не универсальными правильный ответ на шифрование и из этого общего правила не так хороши, как расширенный астера специалистов опыта криптограф.

Приложения, которые не могут изменять их формат сообщений, но без проверки подлинности CBC расшифровки рекомендуется пытаться добавить исправлений, такие как:

- Расшифровка не позволяя дешифратор для проверьте или удалите заполнения:
  - Заполнение, которое было применено по-прежнему должны быть удалены или пропущены, перемещении нагрузку в приложение.
  - Преимуществом является то, что заполнение проверки и удаления могут быть внедрены в другую логику проверки данных приложения. При проверке заполнения и проверке данных может осуществляться в константном времени, уменьшается угроз.
  - Поскольку Интерпретация заполнение изменяется длина предполагаемых сообщения, по-прежнему возможно сведения о времени, извлекаемыми из этого подхода.
- Измените режим заполнения расшифровки ISO10126:
  - Заполнение расшифровки ISO10126 совместим с заполнение шифрования PKCS7 и заполнения ANSIX923 шифрования.
  - Изменение режима уменьшает знаний oracle заполнения на 1 байт, а не весь блок. Однако если содержимое имеет известный нижний колонтитул, например, закрывающий XML-элемент связанных атак можно продолжить взломать оставшуюся часть сообщения.
  - Это также не предотвращает восстановления открытого текста в ситуациях, когда злоумышленник удерживающей открытого текста для шифрования несколько раз со смещением другое сообщение.
- Шлюз оценки для расшифровки вызова ослабить сигнал о времени:
  - Вычисление времени ожидания должно быть не менее сверх максимальное количество времени, могут быть выполнены операции расшифровки для любой сегмент данных, содержащий заполнения.
  - Время вычисления должны выполняться в соответствии с инструкциями в статье [получения отметки времени с высоким разрешением](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), не с помощью <xref:System.Environment.TickCount?displayProperty=nameWithType> (с учетом данных наката over или переполнение) или вычитание двух меток времени системы (изменены NTP ошибки).
  - Время вычислений необходимо включающие операции дешифрования, включая все возможные исключения в управлять или приложений C++, добавленными не только в конце.
  - При успешном или неуспешном завершении будет определено еще, шлюз времени должно возвратить сбой после истечения срока его действия.
- Службы, выполняющих расшифровка без проверки подлинности должны иметь средств мониторинга для обнаружения, что поток сообщения «Недопустимый» будет подключена.
  - Не забывайте, что этот сигнал выполняет ложных положительных результатов (основаниях поврежденные данные) и ложных отрицательных результатов (рассредоточения атаки на достаточно продолжительное время, чтобы избежать обнаружения).

## <a name="finding-vulnerable-code---native-applications"></a>Чтобы найти уязвимым - приложений в машинном коде

Для программ, которые построены на шифрование Windows: библиотеки следующего поколения (CNG):

- Вызов расшифровки [BCryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa375391.aspx), указав `BCRYPT_BLOCK_PADDING` флаг.
- Дескриптор ключа был инициализирован путем вызова [BCryptSetProperty](https://msdn.microsoft.com/library/windows/desktop/aa375504.aspx) с [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) значение `BCRYPT_CHAIN_MODE_CBC`.
  - Поскольку `BCRYPT_CHAIN_MODE_CBC` используется по умолчанию, затронутых код не может иметь присвоено любое значение для `BCRYPT_CHAINING_MODE`.

Для программ, созданных для старых API шифрования Windows:

- Вызов расшифровки [CryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa379913.aspx) с `Final=TRUE`.
- Дескриптор ключа был инициализирован путем вызова [CryptSetKeyParam](https://msdn.microsoft.com/library/windows/desktop/aa380272.aspx) с [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) значение `CRYPT_MODE_CBC`.
  - Поскольку `CRYPT_MODE_CBC` используется по умолчанию, затронутых код не может иметь присвоено любое значение для `KP_MODE`.

## <a name="finding-vulnerable-code---managed-applications"></a>Поиск кода уязвимым - управляемых приложений

- Вызов расшифровки <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> или <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> методы <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.
  - Это включает в себя следующие производные типы в .NET, но может также включать сторонним типам:
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
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> Было задано значение <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, или <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.
  - Поскольку <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> используется по умолчанию, затронутых кода никогда не были назначены <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> свойство.
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> Было задано значение <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>
  - Поскольку <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> используется по умолчанию, затронутых кода никогда не были назначены <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> свойство.

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a>Чтобы найти уязвимым - синтаксиса шифрования сообщений

Сообщение CMS EnvelopedData без проверки подлинности, которого зашифрованное содержимое использует режим CBC AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), (1.3.14.3.2.7) DES, 3DES (1.2.840.113549.3.7) или версии-кандидата 2 (1.2.840.113549.3.2) — уязвимости, также как и в случае сообщений с помощью других алгоритмов шифрования блока в режиме CBC.

Пока потоковых шифров не подвержены данной уязвимости, корпорация Майкрософт рекомендует всегда проверку подлинности данные по проверке ContentEncryptionAlgorithm значение.

Для управляемых приложений EnvelopedData CMS, больших двоичных объектов может быть обнаружено как любое значение, которое передается <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.

Для собственных приложений большой двоичный объект CMS EnvelopedData могут быть обнаружены как любое значение, указанное в дескриптор CMS через [CryptMsgUpdate](https://msdn.microsoft.com/library/windows/desktop/aa380231.aspx) , что приводит к [CMSG_TYPE_PARAM](https://msdn.microsoft.com/library/windows/desktop/aa380227.aspx) — `CMSG_ENVELOPED` и/или дескриптор CMS затем отправляются `CMSG_CTRL_DECRYPT` инструкция через [CryptMsgControl](https://msdn.microsoft.com/library/windows/desktop/aa380220.aspx).

## <a name="vulnerable-code-example---managed"></a>Пример кода уязвим - управляемые

Этот метод считывает файл cookie и расшифровывает его, и отображается без проверки целостности данных. Таким образом содержимое файла cookie, который считывается с помощью данного метода могут подвергнуться атаке пользователь, получивший его или любой злоумышленник получил значение зашифрованного файла cookie.

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

## <a name="example-code-following-recommended-practices---managed"></a>Следующий пример кода рекомендуется выполнять-управляемые

В следующем примере кода используется формат нестандартные сообщения

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

где `cipher_algorithm_id` и `hmac_algorithm_id` идентификаторы алгоритмов являются локальными для приложения (стандартным) представлениями этих алгоритмов. Эти идентификаторы смысл в других частях вашей существующей протокол обмена сообщениями, а не как состояния системы объединенных потока данных.

В этом примере также использует только один главный ключ для получения ключа шифрования и ключ HMAC. Это обеспечивается как для удобства для включения приложения, ключом которых является отдельным элементом в приложение с ключами двумя, а также чтобы стимулировать два ключа для сохранения значений как разные. Он дальнейшей гарантирует, что ключ HMAC и ключ шифрования не удается получить не синхронизированы.

В этом примере не принимает <xref:System.IO.Stream> для шифрования или расшифровки. Текущий делает формат данных один проход шифрования сложно из-за `hmac_tag` значение предшествует зашифрованного текста. Тем не менее этот формат был выбран, поскольку он поддерживает все элементы фиксированного размера с самого начала, чтобы сделать проще, средство синтаксического анализа. Формат данных расшифровка один проход возможна на то, что разработчик cautioned для вызова GetHashAndReset и проверить результаты перед вызовом TransformFinalBlock. Если потокового шифрования является важной, в другом режиме AE будут отличаться.

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
