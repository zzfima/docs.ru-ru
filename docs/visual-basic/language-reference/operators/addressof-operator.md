---
title: "Оператор AddressOf (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 04a7c5be9b890faea561c28715093a271cf9eaa8
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="addressof-operator-visual-basic"></a>Оператор AddressOf (Visual Basic)
Создает экземпляр делегата процедуры, ссылающийся на указанную процедуру.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Части  
 `procedurename`  
 Обязательный. Указывает процедуру, на которые ссылается созданный делегат процедуры.  
  
## <a name="remarks"></a>Примечания  
 `AddressOf` Оператор создает делегат функции, который указывает функции, указанной `procedurename`. Если указанная процедура является методом экземпляра, то делегат функции ссылается на экземпляр и метод. Затем при вызове делегата функции вызывается указанный метод указанного экземпляра.  
  
 `AddressOf` Оператор может использоваться как операнд конструктора делегата, или он может использоваться в контексте, в котором тип делегата можно определить с помощью компилятора.  
  
## <a name="example"></a>Пример  
 В этом примере используется `AddressOf` оператор, чтобы назначить делегата для обработки `Click` событие элемента управления button.  
  
 [!code-vb[VbVbalrDelegates №&8;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `AddressOf` оператор, чтобы назначить функцию запуска для потока.  
  
 [!code-vb[VbVbalrDelegates №&9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)

