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
ms.openlocfilehash: a78189a6b82100665ac07b9d7c89590613ec1e1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745627"
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
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 Как показано в предыдущем примере, можно использовать `Is` оба оператора с ранней привязкой и позднее связывание объектов.  
  
## <a name="see-also"></a>См. также
- [Оператор TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
