---
title: "&quot;As Any&quot; не поддерживается в инструкциях &quot;Declare&quot; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30828
- vbc30828
dev_langs:
- VB
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fb179ae938d4c132f61e2076248729f7ea15a13f
ms.lasthandoff: 03/13/2017

---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a>'As Any' не поддерживается в инструкциях 'Declare'
`Any` Использовался тип данных с помощью `Declare` операторов в Visual Basic 6.0 и более ранних версиях, чтобы разрешить использование аргументов, которые могут содержать данные любого типа. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]поддерживает перегрузку, однако и это делает `Any` устаревший тип данных.  
  
 **Идентификатор ошибки:** BC30828  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Объявления параметров определенного типа, который вы хотите использовать; Например.  
  
     [!code-vb[VbVbalrStatements&#95;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  Используйте <xref:System.Runtime.InteropServices.MarshalAsAttribute>атрибут, чтобы указать `As Any` при `Void*` ожидается вызываемой процедуры.</xref:System.Runtime.InteropServices.MarshalAsAttribute>  
  
     [!code-vb[VbVbalrStatements&#96;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute></xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Пошаговое руководство: Вызов Windows API](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)   
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Создание прототипов в управляемом коде](http://msdn.microsoft.com/library/ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d)
