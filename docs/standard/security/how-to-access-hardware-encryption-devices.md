---
title: Практическое руководство. Доступ к устройствам аппаратного шифрования
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encryption
- key card
- cryptography
- hardware encryption
- CspParameters
ms.assetid: b0e734df-6eb4-4b16-b48c-6f0fe82d5f17
ms.openlocfilehash: d6ee22fd9fb0c11e22ac01ff83b3269e37e37763
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706179"
---
# <a name="how-to-access-hardware-encryption-devices"></a>Практическое руководство. Доступ к устройствам аппаратного шифрования
Класс <xref:System.Security.Cryptography.CspParameters> можно использовать для доступа к устройствам аппаратного шифрования. Например, этот класс можно использовать для интеграции приложения со смарт-картой, аппаратным генератором случайных чисел или аппаратной реализацией определенного алгоритма шифрования.  
  
 Класс <xref:System.Security.Cryptography.CspParameters> создает поставщик служб шифрования (CSP), который обращается к правильно установленному устройству аппаратного шифрования.  Можно проверить доступность CSP, изучив следующий раздел реестра при помощи редактора реестра (Regedit.exe): HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.  
  
### <a name="to-sign-data-using-a-key-card"></a>Подпись данных при помощи карты с ключом  
  
1. Создайте новый экземпляр класса <xref:System.Security.Cryptography.CspParameters>, передав в конструктор целочисленный тип поставщика и имя поставщика.  
  
2. Передайте соответствующие флаги в свойство <xref:System.Security.Cryptography.CspParameters.Flags%2A> созданного объекта <xref:System.Security.Cryptography.CspParameters>.  Например, передайте флаг <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer>.  
  
3. Создайте новый экземпляр класса <xref:System.Security.Cryptography.AsymmetricAlgorithm>(например, класс <xref:System.Security.Cryptography.RSACryptoServiceProvider>), передав объект <xref:System.Security.Cryptography.CspParameters> в конструктор.  
  
4. Подпишите данные при помощи одного из методов `Sign` и проверьте данные, используя один из методов `Verify`.  
  
### <a name="to-generate-a-random-number-using-a-hardware-random-number-generator"></a>Формирование случайного числа при помощи аппаратного генератора случайных чисел  
  
1. Создайте новый экземпляр класса <xref:System.Security.Cryptography.CspParameters>, передав в конструктор целочисленный тип поставщика и имя поставщика.  
  
2. Создайте новый экземпляр <xref:System.Security.Cryptography.RNGCryptoServiceProvider>, передав объект <xref:System.Security.Cryptography.CspParameters> в конструктор.  
  
3. Создайте случайное значение при помощи метода <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> или <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A>.  
  
## <a name="example"></a>Пример  
 В примере кода ниже показано, как подписать данные при помощи смарт-карты.  Этот пример кода создает объект <xref:System.Security.Cryptography.CspParameters>, который предоставляет смарт-карты, а затем инициализирует объект <xref:System.Security.Cryptography.RSACryptoServiceProvider> при помощи CSP.  После этого примера подписывает и проверяет некоторые данные.  
  
 [!code-cpp[Cryptography.SmartCardCSP#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CPP/Cryptography.SmartCardCSP.cpp#1)]
 [!code-csharp[Cryptography.SmartCardCSP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CS/example.cs#1)]
 [!code-vb[Cryptography.SmartCardCSP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Cryptography.SmartCardCSP/VB/example.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- Включите пространства имен <xref:System> и <xref:System.Security.Cryptography>.  
  
- На компьютере должно быть установлено устройство чтения смарт-карт и соответствующие драйвера.  
  
- Необходимо инициализировать объект <xref:System.Security.Cryptography.CspParameters>, используя информацию, характерную для вашего устройства чтения смарт-карт.  Дополнительные сведения см. в документации по устройству чтения смарт-карт.
