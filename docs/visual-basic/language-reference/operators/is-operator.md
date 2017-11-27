---
title: "Оператор Is (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b1f3f0fa1fd782550c08c816f47b7541399198e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
 `Is` Оператор определяет, если два объекта ссылаются на тот же объект. Однако сравнение значений не выполняется. Если `object1` и `object2` ссылаются на точное же экземпляр объекта, `result` — `True`; в противном случае, `result` — `False`.  
  
 `Is`Можно также использовать с `TypeOf` ключевое слово, чтобы сделать `TypeOf`... `Is` выражения, которое проверяет, является ли переменная объекта совместим с типом данных.  
  
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
