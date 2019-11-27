---
title: Оператор GoTo
ms.date: 07/20/2015
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
ms.openlocfilehash: d5cdcd214c9679e245645505fe11cb5d521ce085
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351089"
---
# <a name="goto-statement"></a>Оператор GoTo
Безусловно подразделяется на указанную строку в процедуре.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a>Отделение  
 `line`  
 Обязательно. Метка любой линии.  
  
## <a name="remarks"></a>Примечания  
 Оператор `GoTo` может создать ветвь только для строк в той процедуре, в которой она отображается. Строка должна иметь метку, которая `GoTo` может ссылаться на. Дополнительные сведения см. [в разделе инструкции. Метки](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
> `GoTo`ные инструкции могут усложнить чтение и обслуживание кода. Везде, где это возможно, следует использовать структуру элементов управления. Дополнительные сведения см. в разделе [поток управления](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 Нельзя использовать инструкцию `GoTo` для ветвления извне `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`или `Using`...`End Using` или в метку внутри.  
  
## <a name="branching-and-try-constructions"></a>Ветвление и конструкции try  
 В конструкции `Try`...`Catch`...`Finally` для ветвления с помощью инструкции `GoTo` применяются следующие правила.  
  
|Блок или область|Ветвление вне|Ветвление из внутрь|  
|---------------------|-------------------------------|-------------------------------|  
|блок `Try`|Только из блока `Catch` той же конструкции <sup>1</sup>|Только за пределами всей конструкции|  
|блок `Catch`|Никогда не разрешено|Только за пределами всей конструкции или с блоком `Try` одной конструкции <sup>1</sup>|  
|блок `Finally`|Никогда не разрешено|Никогда не разрешено|  
  
 <sup>1</sup> если одна `Try`...`Catch`...`Finally` вложена в другую, блок `Catch` может выполнить ветвление в блок `Try` на своем собственном уровне вложенности, но не в другой блок `Try`. Вложенная конструкция `Try`...`Catch`...`Finally` должна полностью содержаться в блоке `Try` или `Catch` конструкции, в которой она вложена.  
  
 На следующем рисунке показана одна `Try`ная конструкция, вложенная в другую. Различные ветви между блоками двух конструкций указываются как допустимые или недопустимые.  
  
 ![Графическая схема ветвления в конструкциях Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `GoTo` используется для перехода к меткам линии в процедуре.  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>См. также

- [Оператор Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Оператор Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Оператор While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
