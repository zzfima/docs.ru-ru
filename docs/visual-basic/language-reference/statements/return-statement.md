---
title: Оператор Return (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b66d16a249164b8989f05f10c785b97055bfde9e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="return-statement-visual-basic"></a>Оператор Return (Visual Basic)
Возвращает элемент управления в код, который вызвал `Function`, `Sub`, `Get`, `Set`, или `Operator` процедуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a>Отделение  
 `expression`  
 Требуется в `Function`, `Get`, или `Operator` процедуры. Выражение, представляющее значение, возвращаемое вызывающему коду.  
  
## <a name="remarks"></a>Примечания  
 В `Sub` или `Set` процедуре `Return` оператор эквивалентен `Exit Sub` или `Exit Property` инструкции, и `expression` не должен быть указан.  
  
 В `Function`, `Get`, или `Operator` процедуре `Return` инструкция должна включать `expression`, и `expression` должны иметь тип данных, которое можно преобразовать в тип возвращаемого значения процедуры. В `Function` или `Get` процедуры, также существует возможность назначения выражения имени процедуры для использования в качестве возвращаемого значения и последующего выполнения `Exit Function` или `Exit Property` инструкции. В `Operator` процедуру, необходимо использовать `Return``expression`.  
  
 Можно включить столько `Return` инструкций в той же процедуре соответствующим образом.  
  
> [!NOTE]
>  Код в `Finally` блок выполняется после `Return` инструкции в `Try` или `Catch` блок обнаружен, но перед этим `Return` выполняет инструкцию. Объект `Return` инструкции не могут быть включены в `Finally` блока.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Return` инструкции несколько раз, чтобы возвращать вызывающему коду, если процедуру не нужно ничего.  
  
 [!code-vb[VbVbalrStatements#53](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/return-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
