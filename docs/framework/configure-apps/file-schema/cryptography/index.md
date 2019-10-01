---
title: Схема параметров криптографии
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
ms.openlocfilehash: 474c3274bfba6803ebb17289f138251d755250e4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699800"
---
# <a name="cryptography-settings-schema"></a>Схема параметров криптографии
Схема параметров шифрования содержит элементы, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<cryptoNameMapping >** ](cryptonamemapping-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0cryptoClasses >** ](cryptoclasses-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9[ **&nbsp;2cryptoClass >** ](cryptoclass-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0nameEntry >** ](nameentry-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<oidMap >** ](oidmap-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6[ **\<oidEntry >** ](oidentry-element.md)  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[ **\<cryptoClasses**>](cryptoclasses-element.md)|Содержит список криптографических классов, сопоставленных с понятными именами, указанными в элементе **\<nameEntry>** .|  
|[ **\<cryptoClass**>](cryptoclass-element.md)|Содержит криптографический класс, сопоставленный с понятным именем, указанным в элементе **\<nameEntry>** .|  
|[ **\<cryptographySettings**>](cryptographysettings-element.md)|Содержит параметры шифрования.|  
|[ **\<cryptoNameMapping**>](cryptonamemapping-element.md)|Содержит сопоставления классов с понятными именами.|  
|[Элемент **\<mscorlib>** для параметров шифрования](mscorlib-element-for-cryptography-settings.md)|Содержит элемент **\<cryptographySettings>** .|  
|[ **\<nameEntry>** ](nameentry-element.md)|Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.|  
|[ **\<oidEntry>** ](oidentry-element.md)|Сопоставляет идентификатор объекта (OID) ASN.1 с понятным именем.|  
|[ **\<oidMap>** ](oidmap-element.md)|Содержит сопоставления идентификатора объекта ASN.1 с классами.|  
  
## <a name="see-also"></a>См. также

- [Схема файла конфигурации](../index.md)
- [Cryptographic Services](../../../../standard/security/cryptographic-services.md)
