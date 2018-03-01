---
title: "Анализ других строк в .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Char data type, parsing strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- parsing strings, other strings
- Boolean data type, parsing strings
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 714c361507a95fc5f45efbca79191b17e7917fba
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="parsing-other-strings-in-net"></a>Анализ других строк в .NET
Кроме числовых строк и строк <xref:System.DateTime> вы можете преобразовать строки, представляющих типы <xref:System.Char>, <xref:System.Boolean> или <xref:System.Enum>, в соответствующие типы данных.  
  
## <a name="char"></a>Char  
 Метод статического анализа, связанный с типом данных**Char**, полезен для преобразования строки, содержащей один символ, в его значение в кодировке Юникод. В следующем примере кода выполняется разбор строки в символ Юникода.  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a>Boolean  
 Тип данных **Boolean** содержит метод **Parse**, который можно использовать для преобразования строки, представляющей логическое значение в реальный тип **Boolean**. Этот метод не учитывает регистр и может успешно анализировать строку, содержащую значения "True" или "False". Метод **Parse**, связанный с типом **Boolean**, может также анализировать строки, окруженные пробелами. Если передать ему любую другую строку, создается исключение <xref:System.FormatException>.  
  
 Следующий пример кода применяет метод **Parse** для преобразования строки в логическое значение.  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a>Перечисление  
 Статический метод **Parse** можно использовать, чтобы инициализировать значение строки типом перечисления. Этот метод принимает тип перечисления, для которого нужно выполнить синтаксический анализ, анализируемую строку и необязательное логическое значение, обозначающее учет регистра при анализе. Анализируемая строка может содержать несколько значений, разделенных запятыми; перед этими значениями или после них могут быть один или несколько пробелов. Если строка содержит несколько значений, то возвращаемый объект будет содержать сочетание заданных значений, полученное с использованием побитовой операции OR.  
  
 Следующий пример использует метод **Parse** для преобразования строкового представления в значение перечисления. Перечислению <xref:System.DayOfWeek> присваивается значение **Thursday**, найденное в строке.  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a>См. также  
 [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)  
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)  
 [Преобразование типов в .NET](../../../docs/standard/base-types/type-conversion.md)
