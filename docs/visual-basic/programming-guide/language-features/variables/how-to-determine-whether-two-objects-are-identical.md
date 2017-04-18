---
title: "Практическое руководство: определить, являются ли два объекта идентичными (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- testing, objects
- objects [Visual Basic], comparing
- object variables, determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3a853d9f958829eeb0fb42ecbcdae7ba912c89ed
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Практическое руководство. Определение идентичности двух объектов (Visual Basic)
В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], две ссылки на переменные считаются идентичными, если их указатели совпадают, то есть если обе переменных указывают на один экземпляр класса в памяти. Например, в приложении Windows Forms может потребоваться сделать сравнение, чтобы определить ли текущий экземпляр (`Me`) является таким же, как конкретный экземпляр, такой как `Form2`.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]предоставляет два оператора для сравнения указателей. [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) возвращает `True` Если объекты совпадают и [оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) возвращает `True` , если это не так.  
  
## <a name="determining-if-two-objects-are-identical"></a>Определение, являются ли два объекта идентичными  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Для определения идентичности двух объектов  
  
1.  Настройка `Boolean` выражение для проверки двух объектов.  
  
2.  В проверяемом выражении используйте `Is` оператора с двумя объектами в качестве операндов.  
  
     `Is`Возвращает `True` , если объекты указывают на один и тот же экземпляр класса.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Определение, если два объекта не совпадают  
 Иногда требуется выполнить действие, если два объекта не идентичны, и может быть неудобно объединять `Not` и `Is`, например `If Not obj1 Is obj2`. В этом случае можно использовать `IsNot` оператор.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Чтобы определить, если два объекта не совпадают  
  
1.  Настройка `Boolean` выражение для проверки двух объектов.  
  
2.  В проверяемом выражении используйте `IsNot` оператора с двумя объектами в качестве операндов.  
  
     `IsNot`Возвращает `True` , если объекты не указывают на один и тот же экземпляр класса.  
  
## <a name="example"></a>Пример  
 Следующий пример проверяет пары `Object` переменные, чтобы увидеть, указывают ли они на один экземпляр класса.  
  
 [!code-vb[VbVbalrKeywords&#14;](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 В предыдущем примере отображаются следующие выходные данные.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>См. также  
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md)   
 [Оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Практическое руководство: определение связи между двумя объектами](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
