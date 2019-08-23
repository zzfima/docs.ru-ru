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
ms.openlocfilehash: a7964d01905be4e3dd6e8149e5533e9a2cfd9a71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927630"
---
# <a name="cryptography-settings-schema"></a>Схема параметров криптографии
Схема параметров шифрования содержит элементы, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.  
  
 [ **\<configuration>** ](../configuration-element.md)  
  
 [ **\<mscorlib>** ](mscorlib-element-for-cryptography-settings.md)  
  
 [ **\<cryptographySettings>** ](cryptographysettings-element.md)  
  
 [ **\<cryptoNameMapping>** ](cryptonamemapping-element.md)  
  
 [ **\<cryptoClasses>** ](cryptoclasses-element.md)  
  
 [ **\<cryptoClass>** ](cryptoclass-element.md)  
  
 [ **\<nameEntry>** ](nameentry-element.md)  
  
 [ **\<oidMap>** ](oidmap-element.md)  
  
 [ **\<oidEntry>** ](oidentry-element.md)  
  
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
