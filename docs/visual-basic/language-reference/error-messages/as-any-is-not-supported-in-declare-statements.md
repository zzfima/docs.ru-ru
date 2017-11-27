---
title: "&#39; Как любой &#39; не поддерживается в &#39; Declare &#39; инструкции"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords: BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59120622688ee38d5b8f45c08dfc3ae40711fb8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a>&#39; Как любой &#39; не поддерживается в &#39; Declare &#39; инструкции
`Any` Использование типа данных с `Declare` операторы в Visual Basic 6.0 и более ранних версий, чтобы разрешить использование аргументов, которые могут содержать любой тип данных. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]поддерживает перегрузку, однако и это делает `Any` устаревший тип данных.  
  
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
