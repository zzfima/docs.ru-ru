---
title: "Оператор AddressOf (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 52560a2d9071373fd28f7aad2e485da08324656d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="addressof-operator-visual-basic"></a>Оператор AddressOf (Visual Basic)
Создает экземпляр делегата процедуры, ссылающийся на конкретную процедуру.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Части  
 `procedurename`  
 Обязательный. Указывает процедуру, на которые ссылается созданный делегат процедуры.  
  
## <a name="remarks"></a>Примечания  
 `AddressOf` Оператор создает делегат функции, который указывает функции, указанной `procedurename`. Если указанная процедура является методом экземпляра, то делегат функции ссылается на экземпляр и метод. Затем при вызове функции вызывается указанный метод указанного экземпляра.  
  
 `AddressOf` Оператор можно использовать в качестве операнда конструктора делегата, или он может использоваться в контексте, в котором тип делегата может определяться компилятором.  
  
## <a name="example"></a>Пример  
 В этом примере используется `AddressOf` оператор, чтобы назначить делегата для обработки `Click` события кнопки.  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `AddressOf` оператор, чтобы назначить функцию запуска для потока.  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)
