---
title: "Анализ других строк в .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "тип данных Char, разбор строк"
  - "перечисления [.NET Framework], разбор строк"
  - "базовые типы, разбор строк"
  - "разбор строк, другие строки"
  - "тип данных Boolean, разбор строк"
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Анализ других строк в .NET Framework
Кроме числовых строк и строк <xref:System.DateTime>, можно также разбирать строки, представляющие типы <xref:System.Char>, <xref:System.Boolean> и <xref:System.Enum> в типы данных.  
  
## Char  
 Статический метод разбора, связанный с типом данных **Char**, полезен для преобразования строки, содержащей один знак, в его значение в кодировке Юникод.  В следующем примере кода выполняется разбор строки в знак Юникода.  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## Boolean  
 Тип данных **Boolean** содержит метод **Parse**, который можно использовать для преобразования строки с логическим значением в реальный тип **Boolean**.  Этот метод не учитывает регистр и может успешно разбирать строку, содержащую значения "True" или "False". Метод **Parse**, связанный с типом **Boolean**, может также разбирать строки, окруженные пробелами.  Если передается любая другая строка, то создается исключение <xref:System.FormatException>.  
  
 В следующем примере кода показано использование метода **Parse** для преобразования строки в логическое значение.  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## Перечисление  
 Можно использовать статический метод **Parse**, чтобы инициализировать значение строки типом перечисления.  Этот метод получает тип перечисления для разбора, разбираемую строку и необязательный логический флаг, показывающий, будет ли при разборе учитываться регистр.  Разбираемая строка может содержать несколько значений, разделенных запятыми; перед этими значениями или после них могут быть один или несколько пробелов.  Если строка содержит несколько значений, то возвращаемый объект будет содержать сочетание заданных значений, полученное с использованием поразрядной операции ИЛИ.  
  
 В следующем примере показано использование метода **Parse** для преобразования строкового представления в значение перечисления.  Перечислению <xref:System.DayOfWeek> присваивается значение **Thursday** из строки.  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## См. также  
 [Разбор строк](../../../docs/standard/base-types/parsing-strings.md)   
 [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)   
 [Преобразование типов в .NET Framework](../../../docs/standard/base-types/type-conversion.md)