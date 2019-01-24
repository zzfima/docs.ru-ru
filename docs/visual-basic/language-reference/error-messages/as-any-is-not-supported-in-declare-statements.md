---
title: '&#39;Как какой-либо&#39; не поддерживается в &#39;Declare&#39; инструкций'
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: 560ddc8674718f98f3e1a2f6d4facdb198f5e506
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709867"
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a>&#39;Как какой-либо&#39; не поддерживается в &#39;Declare&#39; инструкций
`Any` Использовался тип данных с помощью `Declare` операторов в Visual Basic 6.0 и более ранних версий, чтобы разрешить использование аргументов, которые могут содержать данные любого типа. Visual Basic поддерживает перегрузку, тем не менее и это делает `Any` устаревший тип данных.  
  
 **Идентификатор ошибки:** BC30828  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Объявите параметры конкретного типа, который вы хотите использовать; Например.  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  Используйте <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут для указания `As Any` при `Void*` ожидается вызываемой процедуры.  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Пошаговое руководство: Вызов API Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Создание прототипов в управляемом коде](../../../framework/interop/creating-prototypes-in-managed-code.md)
