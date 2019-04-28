---
title: Оператор IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: e07a775eec003a3e488f6909181aed3f742b4b91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768356"
---
# <a name="isnot-operator-visual-basic"></a>Оператор IsNot (Visual Basic)
Сравнивает две переменные объектной ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Значение `Boolean`.  
  
 `object1`  
 Обязательный. Любой `Object` переменной или выражения.  
  
 `object2`  
 Обязательный. Любой `Object` переменной или выражения.  
  
## <a name="remarks"></a>Примечания  
 `IsNot` Оператор определяет, если два объекта ссылаются на разные объекты. Тем не менее он не выполняет сравнение значений. Если `object1` и `object2` указывают на точное же экземпляр объекта, `result` — `False`; Если нет, `result` является `True`.  
  
 `IsNot` является противоположностью `Is` оператор. Преимущество `IsNot` — избегать неуклюжим синтаксису `Not` и `Is`, который может быть трудно читать.  
  
 Можно использовать `Is` и `IsNot` операторы для проверки объектов с ранним и поздним связыванием.  
  
> [!NOTE]
>  `IsNot` Оператор не может использоваться для сравнения выражений, возвращенных `TypeOf` оператор. Вместо этого необходимо использовать `Not` и `Is` операторы.  
  
## <a name="example"></a>Пример  
 В следующем примере кода используются как `Is` оператор и `IsNot` оператор для выполнения того же сравнения.  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a>См. также

- [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md)
- [Оператор TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Практическое руководство. Проверка совпадения двух объектов](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
