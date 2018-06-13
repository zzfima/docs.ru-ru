---
title: '&#39;As Any&#39; не поддерживается в &#39;Declare&#39; инструкций'
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: 34beaeb7178645d5a167d1b7b969bb3e4f500e1a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588230"
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a>&#39;As Any&#39; не поддерживается в &#39;Declare&#39; инструкций
`Any` Использование типа данных с `Declare` операторы в Visual Basic 6.0 и более ранних версий, чтобы разрешить использование аргументов, которые могут содержать любой тип данных. Visual Basic поддерживает перегрузку, однако и это делает `Any` устаревший тип данных.  
  
 **Идентификатор ошибки:** BC30828  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Объявите параметры конкретного типа, который вы хотите использовать; Например.  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  Используйте <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут для указания `As Any` при `Void*` ожидается в вызываемой процедуре.  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Пошаговое руководство. Вызов API-интерфейсов Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Создание прототипов в управляемом коде](../../../framework/interop/creating-prototypes-in-managed-code.md)
