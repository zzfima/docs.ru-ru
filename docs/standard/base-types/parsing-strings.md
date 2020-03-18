---
title: Анализ строк в .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
ms.openlocfilehash: e4bf14981e538d95aebac3b0f36d38b61747989f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73084317"
---
# <a name="parsing-strings-in-net"></a>Анализ строк в .NET
Операция синтаксического анализа преобразует строку, представляющую базовый тип .NET, в этот базовый тип. Например, операция синтаксического анализа используется для преобразования строки в число с плавающей запятой или в значение даты и времени. Чаще всего для выполнения операции синтаксического разбора используется метод `Parse`. Поскольку разбор — это операция, обратная форматированию (которое подразумевает преобразование базового типа в строковое представление), то применимы многие схожие правила и условия. Подобно тому, как при форматировании используется объект, реализующий интерфейс <xref:System.IFormatProvider> для предоставления зависящей от языка и региональных параметров информации форматирования, точно так же и при синтаксическом разборе используется объект, реализующий интерфейс <xref:System.IFormatProvider>, чтобы определить, как интерпретировать строковое представление. Дополнительные сведения см. в статье [Типы форматирования в .NET](../../../docs/standard/base-types/formatting-types.md).  
  
## <a name="in-this-section"></a>Содержание  
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
