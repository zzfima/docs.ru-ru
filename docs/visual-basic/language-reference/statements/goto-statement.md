---
title: Оператор GoTo
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22a6315e69cd6c797d462d0835e85bb1dde67dcc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="goto-statement"></a>Оператор GoTo
Осуществляет безусловный переход на указанную строку в процедуре.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
GoTo line  
```  
  
## <a name="part"></a>Отделение  
 `line`  
 Обязательный. Метка строки.  
  
## <a name="remarks"></a>Примечания  
 `GoTo` Оператор может выполнять переход только к строкам в процедуре, в котором он отображается. Строка должна содержать строку, метка `GoTo` могут ссылаться на. Дополнительные сведения см. в разделе [как: метка инструкции](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
>  `GoTo`операторы могут сделать код трудными для понимания и обслуживания. По возможности используйте структуру управления. Дополнительные сведения см. в разделе [поток управления](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 Нельзя использовать `GoTo` инструкции для выхода из блоков `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, или `Using`... `End Using` метку внутри этой конструкции.  
  
## <a name="branching-and-try-constructions"></a>Конструкции Try и ветвления  
 В рамках `Try`... `Catch`... `Finally` конструкция, применяются следующие правила для ветвления с `GoTo` инструкции.  
  
|Блок или область|Ветвление внутрь извне|Ветвление вовне|  
|---------------------|-------------------------------|-------------------------------|  
|`Try`блок|Только из `Catch` блок конструирование же <sup>1</sup>|Только вовне всей конструкции|  
|`Catch`блок|Никогда не допускается|Только вовне всей конструкции или `Try` блок конструирование же <sup>1</sup>|  
|`Finally`блок|Никогда не допускается|Никогда не допускается|  
  
 <sup>1</sup> Если один `Try`... `Catch`... `Finally` вложена в другую, `Catch` блок можно ветвление в `Try` блок в свой собственный уровень вложенности, но не в любой другой `Try` блока. Вложенный `Try`... `Catch`... `Finally` конструкции, которые должны содержаться в полностью `Try` или `Catch` блок конструирование, в течение которого он является вложенным.  
  
 На следующем рисунке показано одно `Try` конструкции, вложенным в другой. Различные ветви между блоками двух конструкций обозначены как допустимое или недопустимое.  
  
 ![Графическая схема ветвления в конструкциях Try](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")  
Допустимые и недопустимые ветви в конструкциях Try  
  
## <a name="example"></a>Пример  
 В следующем примере используется `GoTo` инструкции в ветвь на метки в процедуре.  
  
 [!code-vb[VbVbalrStatements#31](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/goto-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Оператор Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
