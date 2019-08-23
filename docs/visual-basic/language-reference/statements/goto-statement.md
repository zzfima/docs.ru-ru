---
title: Оператор GoTo (Visual Basic)
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
ms.openlocfilehash: 3034c84684e94dfe8c334107a16df8cbd227c4d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912452"
---
# <a name="goto-statement"></a>Оператор GoTo
Безусловно подразделяется на указанную строку в процедуре.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
GoTo line  
```  
  
## <a name="part"></a>Отделение  
 `line`  
 Обязательный. Метка любой линии.  
  
## <a name="remarks"></a>Примечания  
 `GoTo` Оператор может создать ветвь только для строк в процедуре, в которой она отображается. Строка должна иметь метку, которая `GoTo` может ссылаться на. Дополнительные сведения см. в разделе [Практическое руководство. Операторы](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)меток.  
  
> [!NOTE]
> `GoTo`инструкции могут усложнить чтение и поддержку кода. Везде, где это возможно, следует использовать структуру элементов управления. Дополнительные сведения см. в разделе [Поток управления](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 Нельзя использовать `GoTo` оператор для ветвления `For`извне... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With` или`Using`... `End Using` для создания метки в.  
  
## <a name="branching-and-try-constructions"></a>Ветвление и конструкции try  
 `Try`В... `Catch`... для создания ветвления `GoTo` с помощью оператора применяются следующие правила. `Finally`  
  
|Блок или область|Ветвление вне|Ветвление из внутрь|  
|---------------------|-------------------------------|-------------------------------|  
|`Try`блок|Только из `Catch` блока одной конструкции <sup>1</sup>|Только за пределами всей конструкции|  
|`Catch`блок|Никогда не разрешено|Только за пределами всей конструкции или с `Try` блоком той же конструкции <sup>1</sup>|  
|`Finally`блок|Никогда не разрешено|Никогда не разрешено|  
  
 <sup>1</sup> , если `Try`один... `Catch`... Конструкция вложена в другую `Catch` , `Try` блок может выполнять ветвление в блок на своем собственном уровне вложенности, но не в другой `Try` блок. `Finally` Вложенный `Try`... `Catch`... конструкция должна полностью содержаться `Try` в блоке или `Catch` конструкции, внутри которой она вложена. `Finally`  
  
 На следующем рисунке показана `Try` одна конструкция, вложенная в другую. Различные ветви между блоками двух конструкций указываются как допустимые или недопустимые.  
  
 ![Графическая схема ветвления в конструкциях Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>Пример  
 В следующем примере `GoTo` оператор используется для перехода к меткам линии в процедуре.  
  
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
