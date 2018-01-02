---
title: "Настройка криптографических классов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 23bd6007beb870895316a565283ee7e7354c931b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
