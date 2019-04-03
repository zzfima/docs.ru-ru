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
ms.openlocfilehash: a59ff4c956724c614342f0ee4c0622a67f1c25e7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817075"
---
# <a name="is-operator-visual-basic"></a>Оператор Is (Visual Basic)
Сравнивает две переменные объектной ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любой `Boolean` значение.  
  
 `object1`  
 Обязательный. Любой `Object` имя.  
  
 `object2`  
 Обязательный. Любой `Object` имя.  
  
## <a name="remarks"></a>Примечания  
 `Is` Оператор определяет, если два объекта ссылаются на тот же объект. Тем не менее он не выполняет сравнение значений. Если `object1` и `object2` указывают на точное же экземпляр объекта, `result` — `True`; Если нет, `result` является `False`.  
  
 `Is` Можно также использовать с `TypeOf` ключевое слово, чтобы сделать `TypeOf`... `Is` выражение, которое проверяет, является ли совместим с типом данных переменной объекта.  
  
> [!NOTE]
>  `Is` Ключевое слово также используется в [выберите... Оператор выбора](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Is` оператор для сравнения пар ссылки на объекты. Результаты назначаются `Boolean` значение, представляющее ли два объекта идентичны.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Как показано в предыдущем примере, можно использовать `Is` оба оператора с ранней привязкой и позднее связывание объектов.  
  
## <a name="see-also"></a>См. также

- [Оператор TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
