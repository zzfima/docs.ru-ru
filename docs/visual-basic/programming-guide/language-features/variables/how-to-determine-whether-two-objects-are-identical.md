---
title: Практическое руководство. Определение идентичности двух объектов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: bbcac2fc51e57427b125ec2f5e68f017a60186d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650102"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Практическое руководство. Определение идентичности двух объектов (Visual Basic)
В Visual Basic две ссылки на переменные считаются идентичными, если их указатели совпадают, то есть, если обе переменные указывают на один и тот же экземпляр класса в памяти. Например, в приложении Windows Forms, может потребоваться провести сравнение для определения ли текущий экземпляр (`Me`) совпадает со значением конкретного экземпляра, такие как `Form2`.  
  
 Visual Basic предоставляет два оператора для сравнения указателей. [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) возвращает `True` Если объекты совпадают и [оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) возвращает `True` , если это не так.  
  
## <a name="determining-if-two-objects-are-identical"></a>Определение, если два объекта совпадают  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Для определения идентичности двух объектов  
  
1.  Настройка `Boolean` выражение для проверки двух объектов.  
  
2.  В проверяемом выражении используйте `Is` оператора с двумя объектами в качестве операндов.  
  
     `Is` Возвращает `True` , если объекты указывают на один и тот же экземпляр класса.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Определение, если два объекта не совпадают  
 Иногда требуется выполнить действие, если два объекта не идентичны, и может быть неудобно объединять `Not` и `Is`, например `If Not obj1 Is obj2`. В этом случае можно использовать `IsNot` оператор.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Чтобы определить, если два объекта не совпадают  
  
1.  Настройка `Boolean` выражение для проверки двух объектов.  
  
2.  В проверяемом выражении используйте `IsNot` оператора с двумя объектами в качестве операндов.  
  
     `IsNot` Возвращает `True` , если объекты не указывают на один и тот же экземпляр класса.  
  
## <a name="example"></a>Пример  
 Следующий пример проверяет пары `Object` переменные, чтобы увидеть, указывают ли они на один экземпляр класса.  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 В предыдущем примере отображаются следующие выходные данные.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>См. также  
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [Оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Практическое руководство. Определение наличия связи между двумя объектами](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
