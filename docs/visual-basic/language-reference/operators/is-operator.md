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
ms.openlocfilehash: 0351d224d9bf08a8f3ca74090de7b9c51c2c61bf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701365"
---
# <a name="is-operator-visual-basic"></a>Оператор Is (Visual Basic)
Сравнивает две переменные ссылки на объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Обязательный. Любое значение `Boolean`.  
  
 `object1`  
 Обязательный. Любое имя `Object`.  
  
 `object2`  
 Обязательный. Любое имя `Object`.  
  
## <a name="remarks"></a>Примечания  
 Оператор `Is` определяет, ссылаются ли две объектные ссылки на один и тот же объект. Однако сравнение значений не выполняется. Если `object1` и `object2` ссылаются на один и тот же экземпляр объекта, `result` — `True`; в противном случае `result` — `False`.  
  
 `Is` можно также использовать с ключевым словом `TypeOf` для создания выражения `TypeOf`... `Is`, которое проверяет, совместима ли объектная переменная с типом данных.  
  
> [!NOTE]
> Ключевое слово `Is` также используется в [SELECT... Case, инструкция](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Is` используется для сравнения пар ссылок на объекты. Результаты присваиваются значению `Boolean`, показывающему, идентичны ли два объекта.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Как показано в предыдущем примере, оператор `Is` можно использовать для тестирования объектов с ранней и поздней привязкой.  
  
## <a name="see-also"></a>См. также

- [Оператор TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
