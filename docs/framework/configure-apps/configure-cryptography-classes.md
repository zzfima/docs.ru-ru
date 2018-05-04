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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b12d5d95a17439308d79d094e8c22206778f3128
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="configuring-cryptography-classes"></a>Настройка криптографических классов
[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Позволяет администраторам компьютера настраивать алгоритмы шифрования по умолчанию и реализации алгоритма, используемые в .NET Framework и соответствующих приложениях.  Например, предприятие, в котором есть собственная реализация алгоритма шифрования ее можно использовать значение по умолчанию вместо реализации [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]. Несмотря на то, что управляемые приложения, использующие шифрование, всегда можно явно привязать к конкретной реализации, рекомендуется, чтобы они создавали криптографические объекты с помощью системы настройки шифрования.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Отображение имен алгоритмов на криптографические классы](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 Описывает сопоставления имени алгоритма с криптографическим классом.  
  
 [Отображение идентификаторов объектов на криптографические алгоритмы](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 Описание способов сопоставления идентификатора объекта в криптографическому алгоритму.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 Общие сведения о криптографических служб, предоставляемых [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].  
  
 [Схема параметров шифрования](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Описание элементов, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.
