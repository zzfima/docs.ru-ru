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
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 811db42e04e73d7acbc03e303297b19fdf643384
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="parsing-strings-in-net"></a>Анализ строк в .NET
Операция синтаксического анализа преобразует строку, представляющую базовый тип .NET, в этот базовый тип. Например, операция синтаксического анализа используется для преобразования строки в число с плавающей запятой или в значение даты и времени. Чаще всего для выполнения операции синтаксического разбора используется метод `Parse`. Поскольку разбор — это операция, обратная форматированию (которое подразумевает преобразование базового типа в строковое представление), то применимы многие схожие правила и условия. Точно так же, как при форматировании используется объект, реализующий <xref:System.IFormatProvider> интерфейс, предоставляющий язык и региональные параметры сведения о форматировании, при синтаксическом разборе используется объект, реализующий интерфейс <xref:System.IFormatProvider> интерфейс, чтобы определить, как интерпретировать строковое представление . Дополнительные сведения см. в разделе [типы форматирования](../../../docs/standard/base-types/formatting-types.md).  
  
## <a name="in-this-section"></a>Содержание  
 [Анализ числовых строк](../../../docs/standard/base-types/parsing-numeric.md)  
 Описывает способ преобразования строк в числовые типы .NET.  
  
 [Анализ строк даты и времени](../../../docs/standard/base-types/parsing-datetime.md)  
 Описывает способ преобразования строк в .NET **DateTime** типов.  
  
 [Анализ других строк](../../../docs/standard/base-types/parsing-other.md)  
 Содержит сведения о преобразовании строк в **Char**, **логическое**, и **перечисления** типов.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)  
 Описывает базовые понятия форматирования, такие как описатели формата и Поставщики формата.  
  
 [Преобразование типов в .NET](../../../docs/standard/base-types/type-conversion.md)  
 Описывает способ преобразования типов.  
  
 [Базовые типы](../../../docs/standard/base-types/index.md)  
 Описание распространенных операций, которые можно выполнять с базовыми типами .NET.
