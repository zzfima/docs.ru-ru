---
title: Оператор IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 0a83b48e5e415bd6ca0c777cef6d34f7127691b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966926"
---
# <a name="isnot-operator-visual-basic"></a>Оператор IsNot (Visual Basic)
Сравнивает две переменные ссылки на объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Значение `Boolean`.  
  
 `object1`  
 Обязательный. Любая `Object` переменная или выражение.  
  
 `object2`  
 Обязательный. Любая `Object` переменная или выражение.  
  
## <a name="remarks"></a>Примечания  
 Оператор `IsNot` определяет, ссылаются ли две объектные ссылки на разные объекты. Однако сравнение значений не выполняется. Если `object1` и `object2` оба ссылаются на один и тот же экземпляр объекта `result` , `False`имеет значение; если нет, `result` то `True`имеет значение.  
  
 `IsNot`является противоположностью `Is` оператора. Преимущество `IsNot` заключается в том, что можно избежать неудобного `Not` синтаксиса с и `Is`, что может быть трудно читать.  
  
 Операторы `Is` и`IsNot` можно использовать для тестирования объектов с ранней и поздней привязкой.  
  
> [!NOTE]
> Оператор не может использоваться для сравнения выражений, `TypeOf` возвращаемых оператором. `IsNot` Вместо этого необходимо использовать `Not` операторы и. `Is`  
  
## <a name="example"></a>Пример  
 В следующем примере кода используются `Is` оператор `IsNot` и оператор для выполнения одинакового сравнения.  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a>См. также

- [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md)
- [Оператор TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Практическое руководство. Проверка того, совпадают ли два объекта](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
