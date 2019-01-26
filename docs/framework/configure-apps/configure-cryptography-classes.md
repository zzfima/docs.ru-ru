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
ms.openlocfilehash: ba11eed316e227ceae4cb5acecb2b081fa8868f2
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55084410"
---
# <a name="configuring-cryptography-classes"></a>Настройка криптографических классов
[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Позволяет администраторам компьютера настраивать алгоритмы шифрования по умолчанию и реализаций алгоритмов, в .NET Framework и соответствующих приложениях.  Например, в организации, имеет собственную реализацию алгоритма шифрования можно использовать эту реализацию по умолчанию, а не реализации [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]. Несмотря на то, что управляемые приложения, использующие шифрование всегда можно явно привязать к конкретной реализации, рекомендуется, чтобы они создавали криптографические объекты с помощью системы настройки шифрования.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Отображение имен алгоритмов на криптографические классы](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 Описывает способ сопоставления имени алгоритма с криптографическим классом.  
  
 [Отображение идентификаторов объектов на криптографические алгоритмы](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 Описывает способ сопоставления идентификатора объекта в криптографическому алгоритму.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 Общие сведения о криптографических служб, предоставляемых [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].  
  
 [Схема параметров шифрования](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Описание элементов, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.
