---
title: "Анализ строк в .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9c2193dd1b1f3c0478efb5fc9c2b80250ef1878f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="parsing-strings-in-net"></a>Анализ строк в .NET
Операция синтаксического анализа преобразует строку, представляющую базовый тип .NET, в этот базовый тип. Например, операция синтаксического анализа используется для преобразования строки в число с плавающей запятой или в значение даты и времени. Чаще всего для выполнения операции синтаксического разбора используется метод `Parse`. Поскольку разбор — это операция, обратная форматированию (которое подразумевает преобразование базового типа в строковое представление), то применимы многие схожие правила и условия. Подобно тому, как при форматировании используется объект, реализующий интерфейс <xref:System.IFormatProvider> для предоставления зависящей от языка и региональных параметров информации форматирования, точно так же и при синтаксическом разборе используется объект, реализующий интерфейс <xref:System.IFormatProvider>, чтобы определить, как интерпретировать строковое представление. Дополнительные сведения см. в статье [Типы форматирования в .NET](../../../docs/standard/base-types/formatting-types.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Анализ числовых строк](../../../docs/standard/base-types/parsing-numeric.md)  
 Описание преобразования строк в числовые типы .NET.  
  
 [Анализ строк даты и времени](../../../docs/standard/base-types/parsing-datetime.md)  
 Описание преобразования строк в типы **даты и времени** .NET.  
  
 [Анализ других строк](../../../docs/standard/base-types/parsing-other.md)  
 Описание преобразования строк в типы **Char**, **Boolean** и **Enum**.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)  
 Описание базовых концепций форматирования, таких как описатели формата и поставщики формата.  
  
 [Преобразование типов в .NET](../../../docs/standard/base-types/type-conversion.md)  
 Описание процесса преобразования типов.  
  
 [Базовые типы](../../../docs/standard/base-types/index.md)  
 Описание типичных операций, которые можно выполнять с базовыми типами .NET.
