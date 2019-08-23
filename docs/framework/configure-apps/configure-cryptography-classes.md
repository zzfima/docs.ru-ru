---
title: Настройка криптографических классов
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: e53f4c5c9e24fb25b43b7f27b80ab984214eeac2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927772"
---
# <a name="configuring-cryptography-classes"></a>Настройка криптографических классов
Windows SDK позволяет администраторам компьютеров настраивать алгоритмы шифрования по умолчанию и реализации алгоритмов, используемые .NET Framework и соответствующим образом написанными приложениями.  Например, предприятие с собственной реализацией алгоритма шифрования может сделать реализацию по умолчанию вместо реализации, поставляемой в Windows SDK. Несмотря на то, что управляемые приложения, использующие шифрование, всегда могут явно привязываться к определенной реализации, рекомендуется создавать криптографические объекты с помощью системы конфигурации шифрования.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Отображение имен алгоритмов на криптографические классы](map-algorithm-names-to-cryptography-classes.md)  
 Описывает, как сопоставлять имя алгоритма с криптографическим классом.  
  
 [Отображение идентификаторов объектов на криптографические алгоритмы](map-object-identifiers-to-cryptography-algorithms.md)  
 Описывает, как сопоставлять идентификатор объекта с алгоритмом шифрования.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Cryptographic Services](../../standard/security/cryptographic-services.md)  
 Содержит общие сведения о службах шифрования, предоставляемых Windows SDK.  
  
 [Схема параметров шифрования](./file-schema/cryptography/index.md)  
 Описание элементов, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.
