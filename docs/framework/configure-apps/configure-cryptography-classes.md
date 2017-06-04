---
title: "Настройка криптографических классов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "конфигурация приложений .NET Framework, шифрование"
  - "файлы конфигурации [платформа .NET Framework], шифрование"
  - "криптографические алгоритмы"
  - "шифрование, классы"
  - "криптография по умолчанию"
  - "безопасность [платформа .NET Framework], шифрование"
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Настройка криптографических классов
[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] позволяет администраторам компьютера настраивать алгоритмы шифрования по умолчанию, а также их реализации, используемые в .NET Framework и в соответствующих приложениях.  Например, если в организации есть собственная реализация алгоритма шифрования, ее можно использовать по умолчанию вместо реализации из [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].  Хотя управляемые приложения, использующие шифрование, всегда можно явно привязать к конкретной реализации, рекомендуется, чтобы они создавали криптографические объекты с помощью системы настройки шифрования.  
  
## В этом подразделе  
 [Отображение имен алгоритмов на криптографические классы](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 Описание способа сопоставления имени алгоритма с криптографическим классом.  
  
 [Отображение идентификаторов объектов на криптографические алгоритмы](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 Описание способов сопоставления идентификатора объекта с алгоритмом шифрования.  
  
## Связанные подразделы  
 [Службы криптографии](../../../docs/standard/security/cryptographic-services.md)  
 Обзор служб шифрования, имеющихся в [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].  
  
 [Схема параметров криптографии](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Описание элементов, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.