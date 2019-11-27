---
title: Практическое руководство. Проверка совпадения двух объектов
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: 22e8e1e688d9e3bc3804899103ee78814aac235b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343623"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Практическое руководство. Проверка совпадения двух объектов (Visual Basic)
При наличии двух переменных, ссылающихся на объекты, можно использовать либо оператор `Is` или `IsNot`, либо и то, и другое, чтобы определить, ссылаются ли они на один и тот же экземпляр.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>Проверка того, совпадают ли два объекта  
  
- Используйте [оператор is](../../../../visual-basic/language-reference/operators/is-operator.md) или [IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) с двумя переменными в качестве операндов.  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 Может потребоваться выполнить определенное действие в зависимости от того, ссылаются ли два объекта на один и тот же экземпляр. Предыдущий пример сравнивает `c` элемента управления с активным элементом управления в `f`формы. Если нет активного элемента управления или если он существует, но он не является тем же экземпляром элемента управления, что и `c`, то инструкция `If` завершается ошибкой и процедура возвращается без дальнейшей обработки.  
  
 Независимо от того, используется ли `Is` или `IsNot`. Один из них может быть проще читать, чем другой в данном выражении.  
  
## <a name="see-also"></a>См. также

- [Операторы сравнения в Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
