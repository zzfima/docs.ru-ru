---
title: Оператор Return (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: af49ea95d7f9d01072190ac3ccf6ba2f1041347e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957677"
---
# <a name="return-statement-visual-basic"></a>Оператор Return (Visual Basic)
Возвращает управление `Function`коду, который вызвал процедуру `Get`, `Sub`,, `Set`или `Operator` .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a>Отделение  
 `expression`  
 Требуется в `Function`процедуре, `Get`или. `Operator` Выражение, представляющее значение, возвращаемое вызывающему коду.  
  
## <a name="remarks"></a>Примечания  
 `Set` `Exit Property` В процедуре `Sub` `Exit Sub` или инструкция эквивалентна оператору или и`expression` не должна быть указана. `Return`  
  
 `Get` Впроцедуре`Return` ,или`expression`инструкция должна включать оператор и`expression` должен иметь тип данных, преобразуемый в возвращаемый тип процедуры. `Operator` `Function` В процедуре `Get` `Exit Function` или вы также можете назначить выражение имени процедуры, которое будет использоваться в качестве возвращаемого значения, а затем выполнить инструкцию или `Exit Property`. `Function` В процедуре необходимо использовать `Return expression`. `Operator`  
  
 В одной процедуре можно включить `Return` столько инструкций, сколько необходимо.  
  
> [!NOTE]
> Код `Finally` в блоке выполняется `Try` `Return` после обнаружения оператора в блоке или `Catch` , но перед выполнением этой `Return` инструкции. Инструкция не может быть включена `Finally` в блок. `Return`  
  
## <a name="example"></a>Пример  
 В следующем примере `Return` оператор используется несколько раз для возврата к вызывающему коду, если процедура не должна предпринимать никаких других действий.  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a>См. также

- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)
- [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)
- [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
