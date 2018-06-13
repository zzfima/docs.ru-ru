---
title: Оператор Is (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 8beca1dc8788514224f70cacc5b8ede0974f5230
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601954"
---
# <a name="is-operator-visual-basic"></a>Оператор Is (Visual Basic)
Сравнивает две переменные объектной ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательно. Любой `Boolean` значение.  
  
 `object1`  
 Обязательно. Любой `Object` имя.  
  
 `object2`  
 Обязательно. Любой `Object` имя.  
  
## <a name="remarks"></a>Примечания  
 `Is` Оператор определяет, если два объекта ссылаются на тот же объект. Однако сравнение значений не выполняется. Если `object1` и `object2` ссылаются на точное же экземпляр объекта, `result` — `True`; в противном случае, `result` — `False`.  
  
 `Is` Можно также использовать с `TypeOf` ключевое слово, чтобы сделать `TypeOf`... `Is` выражения, которое проверяет, является ли переменная объекта совместим с типом данных.  
  
> [!NOTE]
>  `Is` Также используется ключевое слово в [выберите... Оператор выбора](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Is` оператор для сравнения пар ссылок на объекты. Результаты назначаются `Boolean` значение, представляющее ли два объекта совпадают.  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 Как показано в предыдущем примере, вы можете использовать `Is` оба оператора с ранней привязкой и позднее привязывание объектов.  
  
## <a name="see-also"></a>См. также  
 [Оператор TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
