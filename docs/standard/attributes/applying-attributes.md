---
title: "Применение атрибутов | Microsoft Docs"
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
  - "сборки [платформа .NET Framework], атрибуты"
  - "атрибуты [платформа .NET Framework], применение"
ms.assetid: dd7604eb-9fa3-4b60-b2dd-b47739fa3148
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Применение атрибутов
Используйте следующую процедуру для применения атрибутов к элементам собственного кода.  
  
1.  Определите новый атрибут или используйте существующий, импортировав его пространство имен из .NET Framework.  
  
2.  Примените этот атрибут к элементу кода, поместив его непосредственно перед элементом.  
  
     Каждый язык имеет свой собственный синтаксис атрибутов.  В C\+\+ и C\# атрибут заключается в квадратные скобки и отделяется от элемента пробелами, которые могут содержать разрыв строки.  В Visual Basic атрибут заключается в угловые скобки и должен находиться на той же логической строке. При необходимости вставки разрыва строки может использоваться символ продолжения строки.  В J\# атрибут присоединяется с помощью специального синтаксиса комментариев.  
  
3.  Укажите позиционные и именованные параметры атрибута.  
  
     Позиционные параметры являются обязательными и должны задаваться до всех именованных параметров. Они соответствуют параметрам одного из конструкторов атрибута.  Именованные параметры являются необязательными и соответствуют свойствам атрибута.  В C\+\+, C\# и J\# укажите `name`\=`value` для каждого необязательного параметра, где `name` — это имя свойства.  В Visual Basic укажите `name`:\=`value`.  
  
 При компиляции кода выполняется добавление атрибута в метаданные. Добавленный атрибут становится доступным среде CLR и любому пользовательскому инструменту или приложению через службы отражения среды выполнения.  
  
 По соглашению все имена атрибутов заканчиваются словом Attribute.  Однако в некоторых языках, исполняемых в среде выполнения, например Visual Basic и C\#, не требуется указание полного имени атрибута.  Например, если требуется инициализировать <xref:System.ObsoleteAttribute?displayProperty=fullName>, то можно ссылаться на него как на **Obsolete**.  
  
## Применение атрибута к методу  
 В следующем примере кода показано объявление **System.ObsoleteAttribute**, помечающего код как устаревший.  Атрибуту передается строка `"Will be removed in next version"`.  Этот атрибут вызывает предупреждение компилятора, в котором отображается переданная строка при вызове кода, описываемого данным атрибутом.  
  
 [!code-cpp[Conceptual.Attributes.Usage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#3)]
 [!code-csharp[Conceptual.Attributes.Usage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#3)]
 [!code-vb[Conceptual.Attributes.Usage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#3)]  
  
## Применение атрибутов на уровне сборки  
 Если атрибут нужно применять на уровне сборки, используйте ключевое слово **assembly** \(`Assembly` в Visual Basic\).  В следующем коде показан атрибут **AssemblyTitleAttribute**, применяемый на уровне сборки.  
  
 [!code-cpp[Conceptual.Attributes.Usage#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source1.cpp#2)]
 [!code-csharp[Conceptual.Attributes.Usage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source1.cs#2)]
 [!code-vb[Conceptual.Attributes.Usage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source1.vb#2)]  
  
 При применении этого атрибута строка `"My Assembly"` помещается в манифест сборки в разделе метаданных файла.  Атрибут можно просмотреть с помощью [дизассемблера MSIL \(Ildasm.exe\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) или путем создания пользовательской программы, извлекающей атрибут.  
  
## См. также  
 [Атрибуты](../../../docs/standard/attributes/index.md)   
 [Извлечение информации, сохраненной в атрибуте](../../../docs/standard/attributes/retrieving-information-stored-in-attributes.md)   
 [Concepts](../Topic/Attributed%20Programming%20Concepts.md)   
 [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)