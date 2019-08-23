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
ms.openlocfilehash: a5481a9bce01e84ce4f078335c8cd15a747a3c51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917219"
---
# <a name="is-operator-visual-basic"></a>Оператор Is (Visual Basic)
Сравнивает две переменные ссылки на объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любое `Boolean` значение.  
  
 `object1`  
 Обязательный. Любое `Object` имя.  
  
 `object2`  
 Обязательный. Любое `Object` имя.  
  
## <a name="remarks"></a>Примечания  
 `Is` Оператор определяет, ссылаются ли две объектные ссылки на один и тот же объект. Однако сравнение значений не выполняется. Если `object1` и `object2` оба ссылаются на один и тот же экземпляр объекта `result` , `True`имеет значение; если нет, `result` то `False`имеет значение.  
  
 `Is`также можно использовать с `TypeOf` ключевым словом для `TypeOf`создания... `Is` выражение, которое проверяет, совместима ли объектная переменная с типом данных.  
  
> [!NOTE]
> `Is` Ключевое слово также используется в [SELECT... Case, инструкция](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере `Is` оператор используется для сравнения пар ссылок на объекты. Результаты присваиваются `Boolean` значению, представляющему идентичность двух объектов.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Как показано в предыдущем примере, `Is` оператор можно использовать для тестирования объектов с ранней и поздней привязкой.  
  
## <a name="see-also"></a>См. также

- [Оператор TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
