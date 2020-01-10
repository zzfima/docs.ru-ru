---
title: Модель криптографии .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- cryptography [.NET Framework], model
- encryption [.NET Framework], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
ms.openlocfilehash: f0c00e4cc866c537fe26dd1ad466d6cde95bc608
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706231"
---
# <a name="net-framework-cryptography-model"></a>Модель криптографии .NET Framework

Платформа .NET Framework предоставляет реализации многих стандартных алгоритмов шифрования. Эти алгоритмы просты в использовании и имеют максимально безопасные свойства по умолчанию. Кроме того, криптографическая модель наследования объектов, поточно-ориентированная структура и конфигурация платформы .NET Framework являются чрезвычайно расширяемыми.

## <a name="object-inheritance"></a>Наследование объектов

Система безопасности .NET Framework реализует расширяемую модель наследования производных классов. Иерархия имеет представленный ниже вид.

- Класс типа алгоритма, например <xref:System.Security.Cryptography.SymmetricAlgorithm>, <xref:System.Security.Cryptography.AsymmetricAlgorithm> или <xref:System.Security.Cryptography.HashAlgorithm>. Этот уровень является абстрактным.

- Класс алгоритма, наследующий от класса типа алгоритма, например <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RC2> или <xref:System.Security.Cryptography.ECDiffieHellman>. Этот уровень является абстрактным.

- Реализация класса алгоритма, наследующего от класса алгоритма, например <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider> или <xref:System.Security.Cryptography.ECDiffieHellmanCng>. Этот уровень полностью реализован.

При помощи этой системы производных классов можно легко добавить новый алгоритм или новую реализацию существующего алгоритма. Например, чтобы создать новый алгоритм открытого ключа, можно наследовать от класса <xref:System.Security.Cryptography.AsymmetricAlgorithm>. Чтобы создать новую реализацию определенного алгоритма, можно создать неабстрактный производный класс этого алгоритма.

## <a name="how-algorithms-are-implemented-in-the-net-framework"></a>Реализация алгоритмов в платформе .NET Framework

В качестве примера различных реализаций, доступных для алгоритма, рассмотрим симметричные алгоритмы. Основой для всех симметричных алгоритмов является <xref:System.Security.Cryptography.SymmetricAlgorithm>, который наследуется следующими алгоритмами:

1. <xref:System.Security.Cryptography.Aes>

2. <xref:System.Security.Cryptography.DES>

3. <xref:System.Security.Cryptography.RC2>

4. <xref:System.Security.Cryptography.Rijndael>

5. <xref:System.Security.Cryptography.TripleDES>

<xref:System.Security.Cryptography.Aes> наследуется двумя классами: <xref:System.Security.Cryptography.AesCryptoServiceProvider> и <xref:System.Security.Cryptography.AesManaged>. Класс <xref:System.Security.Cryptography.AesCryptoServiceProvider> является оболочкой реализации CAPI (Windows Cryptography API) для AES, тогда как класс <xref:System.Security.Cryptography.AesManaged> написан полностью в управляемом коде. Имеется также и третий тип реализации — CNG (Cryptography Next Generation), который дополняет реализацию в управляемом коде и реализацию CAPI. Примером алгоритма CNG является <xref:System.Security.Cryptography.ECDiffieHellmanCng>. Алгоритмы CNG доступны в Windows Vista и более поздних версий.

Можно выбрать ту реализацию, которая подходит вам лучше всего.  Реализации в управляемом коде доступны на всех платформах, поддерживающих .NET Framework.  Реализации CAPI доступны в старых операционных системах и больше не разрабатываются. CNG — это самая последняя реализация, при помощи которой будет вестись разработка новых приложений. Однако реализации в управляемом коде не сертифицированы по федеральным стандартам на обработку информации (FIPS) и могут работать медленнее, чем классы-оболочки.

## <a name="stream-design"></a>Поточно-ориентированный подход

Среда CLR использует поточно-ориентированный подход для реализации симметричных алгоритмов и алгоритмов хэширования. Основа такого подхода — класс <xref:System.Security.Cryptography.CryptoStream>, производный от класса <xref:System.IO.Stream>. Основанные на потоках криптографические объекты поддерживают единый стандартный интерфейс (`CryptoStream`) для обработки той части объекта, которая отвечает за передачу данных. Поскольку все объекты построены на базе стандартного интерфейса, можно связывать друг с другом несколько объектов (таких как хэш-объект и объект шифрования), а также выполнять несколько операций с данными без использования промежуточного хранилища. Потоковая модель также позволяет создавать объекты из объектов меньшего размера. Например, объединенный алгоритм шифрования и хэширования можно просмотреть как единый объект потока, хотя этот объект может состоять из набора объектов потока.

## <a name="cryptographic-configuration"></a>Криптографическая конфигурация

Криптографическая конфигурация позволяет разрешить определенную реализацию алгоритма до имени алгоритма, что обеспечивает расширяемость криптографических классов .NET Framework. Вы можете добавить свою собственную аппаратную или программную реализацию алгоритма и сопоставить ее с необходимым именем алгоритма. Если алгоритм не задан в файле конфигурации, используются параметры по умолчанию. Дополнительные сведения о конфигурации криптографии см. в разделе [Настройка криптографических классов](../../../docs/framework/configure-apps/configure-cryptography-classes.md).

## <a name="choosing-an-algorithm"></a>Выбор алгоритма

Алгоритм можно выбирать, исходя из различных причин, например для обеспечения целостности данных, для обеспечения конфиденциальности данных или для создания ключа. Симметричные и хэш-алгоритмы предназначены для защиты данных от нарушения целостности (защита от изменения) или конфиденциальности (защита от просмотра). Хэш-алгоритмы используются в основном для обеспечения целостности данных.

Ниже приведен список рекомендуемых алгоритмов в зависимости от приложения.

- Конфиденциальность данных:

  - <xref:System.Security.Cryptography.Aes>

- Целостность данных:

  - <xref:System.Security.Cryptography.HMACSHA256>

  - <xref:System.Security.Cryptography.HMACSHA512>

- Цифровая подпись.

  - <xref:System.Security.Cryptography.ECDsa>

  - <xref:System.Security.Cryptography.RSA>

- Обмен ключами:

  - <xref:System.Security.Cryptography.ECDiffieHellman>

  - <xref:System.Security.Cryptography.RSA>

- Генерация случайных чисел:

  - <xref:System.Security.Cryptography.RNGCryptoServiceProvider>

- Формирование ключа из пароля:

  - <xref:System.Security.Cryptography.Rfc2898DeriveBytes>

## <a name="see-also"></a>См. также:

- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
