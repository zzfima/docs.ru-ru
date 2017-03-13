---
title: "Практическое руководство. Использование универсального класса (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "параметры типа, определение"
  - "аргументы типа данных, определение"
  - "аргументы [Visual Basic], типы данных"
  - "ключевого слова, использование"
  - "универсальные параметры"
  - "параметры типа данных"
  - "универсальные шаблоны [Visual Basic], об универсальных шаблонах"
  - "типы данных [Visual Basic], в качестве параметров"
  - "типы данных [Visual Basic], в качестве аргументов"
  - "параметры, типы"
  - "типы [Visual Basic], универсальные"
  - "параметры, универсальные"
  - "универсальные шаблоны [Visual Basic], создание универсальных типов"
  - "аргументы типа данных"
  - "параметры, тип данных"
  - "параметры типа данных, определение"
  - "аргументы типа, определение"
  - "аргументы [Visual Basic], тип"
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# Практическое руководство. Использование универсального класса (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Класс, принимающий *параметры типа*, называется *универсальным*. При использовании универсального класса из него можно создать *сконструированный класс*, указав *аргумент типа* для каждого из этих параметров. После этого можно объявить переменную типа сконструированного класса, а также создать экземпляр такого класса и присвоить его этой переменной.  
  
 Помимо классов, можно определять и использовать универсальные структуры, интерфейсы, процедуры и делегаты.  
  
 В следующей процедуре используется универсальный класс, определенный в [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)], и создается его экземпляр.  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a>Использование класса, который принимает параметр типа  
  
1.  В начале файла c исходным кодом добавьте [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md), чтобы импортировать пространство имен <xref:System.Collections.Generic?displayProperty=fullName>. Это даст возможность ссылаться на класс <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>, не определяя его полностью, и отличать его от других классов очереди, например <xref:System.Collections.Queue?displayProperty=fullName>.  
  
2.  Создайте объект обычным способом, но добавьте `(Of` `type``)` сразу после имени класса.  
  
     В приведенном ниже примере с помощью класса <xref:System.Collections.Generic.Queue%601?displayProperty=fullName> создаются два объекта очереди, содержащие элементы разных типов данных. Он добавляет элементы в конец каждой очереди и затем удаляет и отображает элементы из начала каждой очереди.  
  
     [!code-vb[VbVbalrDataTypes#9](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)   
 [Предложение Of (Visual Basic)](../../../../visual-basic/language-reference/statements/of-clause.md)   
 [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Практическое руководство. Определение класса, реализующего одинаковую функциональность для различных типов данных (Visual Basic)](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)   
 [Итераторы](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)