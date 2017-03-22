---
title: "Практическое руководство: использование универсального класса (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- type parameters, defining
- data type arguments, defining
- arguments [Visual Basic], data types
- Of keyword, using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters, type
- types [Visual Basic], generic
- parameters, generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters, data type
- data type parameters, defining
- type arguments, defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
caps.latest.revision: 24
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: eeb55be1c368e9ca80ab94de814a5e2ba9bc9f1f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-a-generic-class-visual-basic"></a>Практическое руководство. Использование универсального класса (Visual Basic)
Класс, принимающий *параметры типа*, называется *универсальным*. При использовании универсального класса из него можно создать *сконструированный класс*, указав *аргумент типа* для каждого из этих параметров. После этого можно объявить переменную типа сконструированного класса, а также создать экземпляр такого класса и присвоить его этой переменной.  
  
 Помимо классов, можно определять и использовать универсальные структуры, интерфейсы, процедуры и делегаты.  
  
 В следующей процедуре используется универсальный класс, определенный в [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], и создается его экземпляр.  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a>Использование класса, который принимает параметр типа  
  
1.  В начале файла исходного кода, включают [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) Импорт <xref:System.Collections.Generic?displayProperty=fullName>имен.</xref:System.Collections.Generic?displayProperty=fullName> Это позволяет ссылаться на <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>класс без необходимости полного имени, чтобы отличить его от других классов очереди, например <xref:System.Collections.Queue?displayProperty=fullName>.</xref:System.Collections.Queue?displayProperty=fullName> </xref:System.Collections.Generic.Queue%601?displayProperty=fullName>  
  
2.  Создайте объект обычным способом, но добавьте `(Of` `type``)` сразу после имени класса.  
  
     В следующем примере используется тот же класс (<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>) для создания двух объектов очередей, содержащих элементы различных типов данных.</xref:System.Collections.Generic.Queue%601?displayProperty=fullName> Он добавляет элементы в конец каждой очереди и затем удаляет и отображает элементы из начала каждой очереди.  
  
     [!code-vb[VbVbalrDataTypes №&9;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3)   
 [Предложение Of (Visual Basic)](../../../../visual-basic/language-reference/statements/of-clause.md)   
 [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Практическое руководство. Определение класса, реализующего одинаковую функциональность для различных типов данных (Visual Basic)](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)   
 [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)
