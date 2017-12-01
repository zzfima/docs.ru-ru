---
title: "Разбор других строк в .NET"
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
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: edd48993f50ec8b91ba7941a682d7de9f22aa12e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-other-strings-in-net"></a>Разбор других строк в .NET
В дополнение к числовым и <xref:System.DateTime> строки, можно также проанализировать строк, представляющих типы <xref:System.Char>, <xref:System.Boolean>, и <xref:System.Enum> в типы данных.  
  
## <a name="char"></a>Char  
 Метод статического анализа, связанный с типом данных**Char**, полезен для преобразования строки, содержащей один символ, в его значение в кодировке Юникод. В следующем примере кода выполняется разбор строки в символ Юникода.  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a>Boolean  
 **Логическое** содержит тип данных **проанализировать** метод, который можно использовать для преобразования строки, которая представляет логическое значение, в фактический **логическое** типа. Этот метод не учитывает регистр и может успешно анализировать строку, содержащую значения "True" или "False". **Проанализировать** метод, связанный с **логическое** тип также можно провести синтаксический анализ строки, окруженные пробельные символы. Если передается любая другая строка, <xref:System.FormatException> возникает исключение.  
  
 Следующий пример кода использует **проанализировать** метод для преобразования строки в логическое значение.  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a>Перечисление  
 Статический метод **Parse** можно использовать, чтобы инициализировать значение строки типом перечисления. Этот метод принимает разборе тип перечисления, строка для анализа и необязательный логический флаг, указывающее, является ли синтаксический анализ с учетом регистра. Анализируемая строка может содержать несколько значений, разделенных запятыми; перед этими значениями или после них могут быть один или несколько пробелов. Если строка содержит несколько значений, то возвращаемый объект будет содержать сочетание заданных значений, полученное с использованием побитовой операции OR.  
  
 В следующем примере используется **проанализировать** метод для преобразования строкового представления в значение перечисления. <xref:System.DayOfWeek> Инициализируется значением перечисления **четверг** из строки.  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a>См. также  
 [Анализ строк в .NET Framework](../../../docs/standard/base-types/parsing-strings.md)  
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)  
 [Преобразование типов в .NET](../../../docs/standard/base-types/type-conversion.md)
