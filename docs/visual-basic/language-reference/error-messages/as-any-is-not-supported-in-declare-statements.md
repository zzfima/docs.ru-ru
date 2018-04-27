---
title: '&#39;As Any&#39; не поддерживается в &#39;Declare&#39; инструкций'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d8146e339ac5cb005b99c9a1e02f1cd248c4558b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a><span data-ttu-id="d0ff4-102">&#39;As Any&#39; не поддерживается в &#39;Declare&#39; инструкций</span><span class="sxs-lookup"><span data-stu-id="d0ff4-102">&#39;As Any&#39; is not supported in &#39;Declare&#39; statements</span></span>
<span data-ttu-id="d0ff4-103">`Any` Использование типа данных с `Declare` операторы в Visual Basic 6.0 и более ранних версий, чтобы разрешить использование аргументов, которые могут содержать любой тип данных.</span><span class="sxs-lookup"><span data-stu-id="d0ff4-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="d0ff4-104">Visual Basic поддерживает перегрузку, однако и это делает `Any` устаревший тип данных.</span><span class="sxs-lookup"><span data-stu-id="d0ff4-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="d0ff4-105">**Идентификатор ошибки:** BC30828</span><span class="sxs-lookup"><span data-stu-id="d0ff4-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d0ff4-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d0ff4-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="d0ff4-107">Объявите параметры конкретного типа, который вы хотите использовать; Например.</span><span class="sxs-lookup"><span data-stu-id="d0ff4-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  <span data-ttu-id="d0ff4-108">Используйте <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут для указания `As Any` при `Void*` ожидается в вызываемой процедуре.</span><span class="sxs-lookup"><span data-stu-id="d0ff4-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d0ff4-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d0ff4-109">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="d0ff4-110">Пошаговое руководство. Вызов API-интерфейсов Windows</span><span class="sxs-lookup"><span data-stu-id="d0ff4-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="d0ff4-111">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="d0ff4-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="d0ff4-112">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="d0ff4-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
