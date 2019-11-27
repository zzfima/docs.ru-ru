---
title: Практическое руководство. Определение идентичности двух объектов
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 5deebd4ffc5b277c94f5ae36c00fd6e5010a1551
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348601"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Практическое руководство. Определение идентичности двух объектов (Visual Basic)
В Visual Basic две ссылки на переменные считаются идентичными, если их указатели одинаковы, то есть если обе переменные указывают на один и тот же экземпляр класса в памяти. Например, в Windows Forms приложении может потребоваться выполнить сравнение, чтобы определить, совпадает ли текущий экземпляр (`Me`) с определенным экземпляром, например `Form2`.  
  
 Visual Basic предоставляет два оператора для сравнения указателей. [Оператор is](../../../../visual-basic/language-reference/operators/is-operator.md) возвращает `True`, если объекты идентичны, а [оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) возвращает `True`, если это не так.  
  
## <a name="determining-if-two-objects-are-identical"></a>Определение идентичности двух объектов  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Определение идентичности двух объектов  
  
1. Настройте `Boolean` выражение для проверки двух объектов.  
  
2. В тестовом выражении используйте оператор `Is` с двумя объектами в качестве операндов.  
  
     `Is` возвращает `True`, если объекты указывают на один и тот же экземпляр класса.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Определение того, что два объекта не идентичны  
 Иногда требуется выполнить действие, если два объекта не идентичны, и может быть неудобно объединять `Not` и `Is`, например `If Not obj1 Is obj2`. В этом случае можно использовать оператор `IsNot`.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Определение того, что два объекта не идентичны  
  
1. Настройте `Boolean` выражение для проверки двух объектов.  
  
2. В тестовом выражении используйте оператор `IsNot` с двумя объектами в качестве операндов.  
  
     `IsNot` возвращает `True`, если объекты не указывают на один и тот же экземпляр класса.  
  
## <a name="example"></a>Пример  
 В следующем примере проверяются пары `Object` переменных, чтобы определить, указывают ли они на один и тот же экземпляр класса.  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 В предыдущем примере отображаются следующие выходные данные.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>См. также

- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md)
- [Оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Практическое руководство. Определение наличия связи между двумя объектами](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
