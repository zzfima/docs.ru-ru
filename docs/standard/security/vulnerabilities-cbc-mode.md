---
title: Время уязвимостей с помощью режима CBC Симметричная расшифровка с помощью заполнения
description: Узнайте, как для обнаружения и устранения уязвимостей, о времени с помощью Симметричная расшифровка режим сцепления блоков шифра (CBC) с помощью заполнения.
ms.date: 06/12/2018
author: blowdart
ms.author: mairaw
ms.openlocfilehash: 6d16b6849bfd4744f1828cda38a537f842243c1d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205105"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a>Время уязвимостей с помощью режима CBC Симметричная расшифровка с помощью заполнения

Корпорация Майкрософт считает, что он больше не безопасные для расшифровки данных, зашифрованных с режим сцепления блоков шифра (CBC), присущая симметричному шифрованию, если проверяемый заполнения был применен без гарантируя целостность зашифрованных данных, за исключением особых в других обстоятельствах. Этот judgement основан на криптографических исследованиях, известные на данный момент. 

## <a name="introduction"></a>Вступление

Атака на заполнение oracle — это тип атаки зашифрованных данных, который позволяет злоумышленнику для расшифровки содержимого данных, не зная ключа.

Тип данных oracle относится к «тип учетной записи» которых дает злоумышленнику информацию о ли обучаться действии правильно или не. Представьте себе воспроизведение на доске или карт игры с дочерним. При ее лиц подсвечено будет с большой смайлик, так как она полагает, что она должна хорошо переход, который является oracle. Как противником, можно использовать этот oracle в соответствии с планом следующего перехода.

Заполнение составляет определенный термин шифрования. Некоторые старые шифры, которые являются алгоритмы, используемые для шифрования данных, работать на блоки данных, где каждый блок имеет фиксированный размер. Если данные, которые вы хотите зашифровать не правильного размера для заполнения в блоках, данных заполняется в том случае, пока получит. Многие виды заполнения требуют этого дополнения, чтобы всегда присутствовать, даже если исходная входная была подходящего размера. Это позволяет дополнения, чтобы всегда безопасно удалить после расшифровки.

Объединения две вещи, реализации программы с oracle заполнения показывает, имеет ли расшифрованные данные допустимым заполнения. Oracle может быть что-то просто возвращает значение, говорит: «Неправильному заполнению» или более сложная операция, например значительно разных время не является допустимым блоком, в отличие от недопустимый блок обработки.

Шифры блочным имеется еще одно свойство, — режим, который определяет связь данных в первом блоке данных во втором блоке, и так далее. Одна из наиболее часто используемые режимы — CBC. CBC вводит начальной случайных блок, известные как вектор инициализации (IV) и объединяет предыдущего блока с результатом статического шифрования, чтобы сделать его таким образом, шифрование и то же сообщение с тем же ключом не всегда создает такие же выходные данные зашифрованных.

Злоумышленник может использовать заполнение oracle, в сочетании с структуру данных CBC, для отправки сообщений слегка измененный код, который предоставляет oracle и поддерживать отправку данных, пока oracle уведомляющее правильности данных. Из этого ответа злоумышленник может расшифровать сообщение байт за байтом.

Современные компьютерные сети являются такие высокого качества, что злоумышленник может обнаружить небольшого различия при внутреннем (менее 0,1 мс), время в удаленных системах. Приложения, которые предполагается, что успешной расшифровки может произойти только в том случае, если данные не было незаконно может быть уязвим для атак из средств, предназначенных для наблюдения за различия в успешных и неуспешных расшифровки. Хотя это различие времени может быть более значимыми в некоторых языков и библиотек, чем другие, теперь считается что это практические угроз для всех языков и библиотек, когда ответ приложения сбой извлекается в учетную запись.

Эта атака зависит от возможности для изменения зашифрованных данных и проверьте результат с oracle. Единственный способ полностью устранить атаки — обнаружение изменений к зашифрованным данным и не будет выполнять каких-либо действий с ним. Стандартный способ сделать это заключается в том, для создания подписи для данных и проверки подписи, прежде, чем любые операции выполнялись. Подпись должна располагаться проверяемых, не может быть создан злоумышленником, в противном случае они бы изменить зашифрованные данные, а затем вычисления новые сигнатуры на основе измененных данных. Один из распространенных типов соответствующей подписью называется код проверки подлинности сообщения (HMAC). Код HMAC отличается от контрольной суммы, в том, что он принимает секретный ключ, известных только пользователю, создания HMAC и проверки его пользователю. Даже при отсутствии ключа не могут производить правильный HMAC. При получении данных, следует воспользоваться зашифрованные данные, независимо друг от друга вычисления HMAC, с помощью секретного ключа вы отправитель общего ресурса, а затем сравнить вычисляемые HMAC, они отправлены по одному. Это сравнение должно быть константном времени, в противном случае вы добавили другой выявляемых oracle, что различные типы атак.

Таким образом для использования дополняются блочные шифры CBC безопасно, их необходимо объединить код HMAC (или другой проверки целостности данных), можно проверить с помощью сравнения константном времени перед попыткой для расшифровки данных. Так как все сообщения измененных принимать то же время сумма на выдачу отклика, атаки блокируется.

## <a name="who-is-vulnerable"></a>Кто уязвим

Эта уязвимость относится к управляемым и машинным приложения, которое выполняет свои собственные шифрования и расшифровки. Сюда входят, например:

- Приложение, шифрует файл cookie для расшифровки более поздней версии на сервере.
- Приложение базы данных, которое предоставляет пользователям для вставки данных в таблицы, столбцы которых затем расшифрованы лицом.
- Приложение передачи данных, которое использует шифрование с помощью общего ключа для защиты передаваемых данных.
- Приложение, которое шифрует и расшифровывает сообщения «внутри» TLS-туннеля.

Обратите внимание на то, что с помощью только TLS может не защищает вас в этих сценариях.

Уязвимого приложения:

- Расшифровывает данные с помощью режима шифра CBC с режимом проверяемых заполнения, например PKCS #7 или ANSI X.923.
- Выполняет расшифровку без выполнять проверку целостности данных (через MAC или асимметричные подписи).

Это также применимо для приложений, построенных на основе абстракции поверх этих примитивов, таких как структура EnvelopedData Cryptographic Message Syntax (PKCS #7/CMS).

## <a name="related-areas-of-concern"></a>Связанные проблемные области

Справочные материалы привело Майкрософт для дальнейшего было бы заботиться о CBC сообщений, которые заполняются ISO 10126-эквивалент padding, если сообщение содержит структуру хорошо известного или какого- либо нижний колонтитул. Например содержимое, подготовленных в соответствии с правилами W3C XML Encryption Syntax и рекомендации по обработке (xmlenc EncryptedXml). Хотя во время считалось соответствующие рекомендации консорциума W3C для подписи сообщения, а затем зашифровать, теперь рекомендуется всегда делаем шифрование then подписью.

Разработчики приложений должны всегда учитывать проверка применимости асимметричный ключ подписи, как отсутствует отношение доверия, присущие между асимметричного ключа и случайное сообщение.

## <a name="details"></a>Подробные сведения

Исторически сложилось так, что произошел согласие, очень важно для шифрования и проверки подлинности важные данные, с помощью средств подписи HMAC или RSA. Тем не менее было меньше четкие инструкции о том, как виртуализация операции шифрования и проверки подлинности. Из-за этой уязвимости, описанные в этой статье рекомендации корпорации Майкрософт — теперь всегда использовать парадигму «шифрования затем входа». То есть сначала шифрование данных с помощью симметричного ключа, а затем вычислений MAC или асимметричные подписи над зашифрованного текста (зашифрованные данные). При расшифровке данных, выполните обратное. Во-первых Подтвердите MAC или подпись зашифрованного текста, а затем расшифровать его.

Класс уязвимостей, известные как «padding атак oracle» известные существовать более 10 лет. Эти уязвимости позволяют злоумышленнику расшифровать данные, зашифрованные алгоритмов симметричного блочного, таких как AES и 3DES, используя не более 4096 попыток каждого блока данных. Эти уязвимости сделать использование тот факт, что блокировка шифры чаще всего используются с данными проверяемых заполнения в конце. Найден, что если злоумышленник может искажать зашифрованные данные и узнать ли незаконное изменение вызвало ошибку в формате заполнения в конце, злоумышленник может расшифровать данные.

Изначально практические атаки были основаны на службы, которые возвращает различных кодов ошибок зависимости от того, была ли заполнение правильной, например уязвимости ASP.NET [MS10-070](https://technet.microsoft.com/library/security/ms10-070.aspx). Тем не менее мы теперь уверены, что оно является удобным для проведения подобных атак, использующих только различия по синхронизации между обработки допустимых и недопустимых заполнения.

Условии, что схема шифрования использует подпись и проверка подписи выполняется с предопределенной среды выполнения для данной длины данных (вне зависимости от содержимого), без передачи сведений, можно проверить целостность данных Злоумышленник с помощью [канала со стороны](https://en.wikipedia.org/wiki/Side-channel_attack). Поскольку проверки целостности отклоняет любые искаженные сообщения, устранения угроз oracle заполнения.

## <a name="guidance"></a>Руководство

В первую очередь Корпорация Майкрософт рекомендует, что любые данные, которые имеет конфиденциальность должен передаваться через слой безопасности TLS (Transport), унаследованный от него к Secure Sockets Layer (SSL).

Далее следует проанализируйте приложения:

- Понять, какие шифрования, выполнении и точно какие Шифрование обеспечивается корпорацией платформ и API, вы используете.
- Быть уверенным, что каждый использования на каждом уровне симметричный [алгоритм шифрования блока](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), такие как AES и 3DES, в режиме CBC внедрить использование проверку целостности данных, ключом которого является секрет (асимметричные подписи, код HMAC, или чтобы изменить режим шифрования для [проверку подлинности шифрования](https://en.wikipedia.org/wiki/Authenticated_encryption) режим (AE), как GCM или CCM).

На основе проведенных исследований, обычно считается, если действия проверки подлинности и шифрования выполняются независимо друг от друга не AE режимов шифрования, проверки подлинности зашифрованного текста (шифрование, затем — знак) лучше всего Общие. Однако не опасно правильный ответ, для шифрования и этот образ не так хороши, как Расширенный совет из профессиональных криптограф.

Приложения, которые не могут изменять их формат обмена сообщениями, но без проверки подлинности расшифровки CBC рекомендуется пытаться добавить Устранение угроз, таких как:

- Расшифровка не позволяя дешифратора проверить и удалить заполнение:
  - Любое заполнение, которая была применена по-прежнему должен быть удален или игнорировать, вы перемещаете нагрузку в приложение.
  - Преимущество в том, что заполнение проверки и удаления могут быть включены в другую логику проверки данных приложения. Если проверка заполнения и проверке данных может осуществляться в константном времени, сокращается угрозы.
  - Так как Интерпретация заполнение меняется длина предполагаемых сообщения, по-прежнему возможны сведения о времени, созданный на основе этого подхода.
- Измените режим заполнения расшифровки ISO10126:
  - Заполнение расшифровки ISO10126 совместим с заполнение шифрования PKCS7 и заполнение ANSIX923 шифрования.
  - Изменение режима позволяет сократить набор знаний oracle заполнения 1 байту, а не весь блок. Тем не менее если содержимое имеет известный нижний колонтитул, например закрывающего XML-элемента, связанные атак можно продолжать атаковать остальную часть сообщения.
  - Кроме того, это не означает восстановления открытого текста в ситуациях, где злоумышленник может приводить открытого текста должны шифроваться со смещением другое сообщение несколько раз.
- Шлюз оценки ослабление сигнала о времени вызова расшифровки:
  - Вычисление времени удержания необходимо иметь как минимум, превышающий максимальный объем времени, которые могут быть выполнены операции расшифровки для любой сегмент данных, содержащий заполнения.
  - Время вычисления должны выполняться в соответствии с инструкциями в [получения отметки времени с высоким разрешением](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), не с помощью <xref:System.Environment.TickCount?displayProperty=nameWithType> (при условии наката over/переполнением) или вычитания две метки времени системы (при условии коррекции NTP ошибки).
  - Время вычислений должен быть включают в себя операции расшифровки, включая все возможные исключения в под или приложений C++, входные данные не только в конце.
  - Если было еще определено об успехе или неудаче, gate времени необходимо вернуть сбой, когда истечет срок его действия.
- Службы, которые выполняются без проверки подлинности расшифровки должны иметь наблюдения для обнаружения, что представила «недопустимый» сообщения были переданы через.
  - Имейте в виду, что этот сигнал выполняет ложных срабатываний (законно поврежденные данные) и ложных отрицательных результатов (рассредоточения атаки через достаточно долго, чтобы избежать обнаружения).

## <a name="finding-vulnerable-code---native-applications"></a>Поиск уязвимого кода - собственных приложений

Для программ, рассчитанных криптографии Windows: библиотека следующего поколения (CNG):

- Вызов расшифровки [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), указав `BCRYPT_BLOCK_PADDING` флаг.
- Дескриптор ключа инициализации, вызвав [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) с [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) присвоено `BCRYPT_CHAIN_MODE_CBC`.
  - Так как `BCRYPT_CHAIN_MODE_CBC` используется по умолчанию, затронутых код не может иметь назначить любое значение для `BCRYPT_CHAINING_MODE`.

Для программ, созданных с помощью более старых API шифрования Windows:

- Вызов расшифровки [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) с `Final=TRUE`.
- Дескриптор ключа инициализации, вызвав [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) с [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) присвоено `CRYPT_MODE_CBC`.
  - Так как `CRYPT_MODE_CBC` используется по умолчанию, затронутых код не может иметь назначить любое значение для `KP_MODE`.

## <a name="finding-vulnerable-code---managed-applications"></a>Поиск уязвимого кода - приложений с управляемым кодом

- Вызов расшифровки <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> или <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> методы <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.
  - Это включает в себя следующие производных типов в .NET, но может также включать сторонние типы:
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
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> Было установлено на <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, или <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.
  - Так как <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> используется по умолчанию, затронутых код может никогда не были назначены <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> свойство.
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> Было установлено на <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>
  - Так как <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> используется по умолчанию, затронутых код может никогда не были назначены <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> свойство.

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a>Поиск уязвимого кода - синтаксис криптографического сообщения

Сообщения CMS EnvelopedData, зашифрованное содержимое использует режим CBC AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), (1.3.14.3.2.7) DES, 3DES (1.2.840.113549.3.7) или версии-кандидата 2 (1.2.840.113549.3.2) — уязвимости, также как и в случае сообщений с помощью любой другие алгоритмы блочного шифра в режиме CBC.

Хотя потоковых шифров, не подвержены влиянию этой уязвимости, корпорация Майкрософт рекомендует всегда проверки ContentEncryptionAlgorithm значения проверки подлинности данные.

Для управляемых приложений, EnvelopedData CMS, большой двоичный объект может быть обнаружено в любое значение, которое передается <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.

Для собственных приложений, CMS EnvelopedData BLOB-объекта могут быть обнаружены как любое значение, указанное на дескриптор CMS с помощью [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) , что приводит к [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) является `CMSG_ENVELOPED` и/или дескриптор CMS позже отправляются `CMSG_CTRL_DECRYPT` инструкции с помощью [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).

## <a name="vulnerable-code-example---managed"></a>Пример уязвимого кода — управляемые

Этот метод считывает файл cookie и расшифровывает его, и проверка целостности данных является видимым. Таким образом содержимое файла cookie, который считывается с помощью данного метода могут подвергнуться атаке пользователь, получивший его или любой злоумышленник получил значение зашифрованного файла cookie.

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

## <a name="example-code-following-recommended-practices---managed"></a>Следующий пример кода, рекомендуется использовать методы — управляемые

В следующем примере кода используется формат нестандартных сообщений

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

где `cipher_algorithm_id` и `hmac_algorithm_id` алгоритм представляют собой локальную (нестандартным) представления этих алгоритмов. Эти идентификаторы смысл в других частях вашей существующей протокол обмена сообщениями, а не как исходного сцепленные потока данных.

В этом примере также использует только один главный ключ для получения ключа шифрования и ключа HMAC. Оно предоставляется только в качестве удобства для включения приложения, ключом которого является отдельным элементом, в приложение с ключом двумя и поощрить, сохраняя два ключа, как разные значения. Дальнейшей гарантирует, что ключ HMAC и ключ шифрования не окажутся не синхронизированы.

В этом примере не принимает <xref:System.IO.Stream> для шифрования или расшифровки. Текущий использует формат данных однопроходное шифрования сложным из-за `hmac_tag` значение предшествует зашифрованный текст. Тем не менее этот формат был выбран, поскольку он поддерживает все элементы фиксированного размера в начале, чтобы не усложнять средство синтаксического анализа. Формат данных расшифровка однопроходное есть вероятность, хоть разработчик предупреждение для вызова GetHashAndReset и проверьте результат перед вызовом TransformFinalBlock. Если важно шифрования потоковой передачи, затем в другой режим AE может потребоваться.

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
