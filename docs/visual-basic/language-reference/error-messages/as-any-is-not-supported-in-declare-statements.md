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
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a><span data-ttu-id="4976b-102">&#39;As Any&#39; не поддерживается в &#39;Declare&#39; инструкций</span><span class="sxs-lookup"><span data-stu-id="4976b-102">&#39;As Any&#39; is not supported in &#39;Declare&#39; statements</span></span>
<span data-ttu-id="4976b-103">`Any` Использование типа данных с `Declare` операторы в Visual Basic 6.0 и более ранних версий, чтобы разрешить использование аргументов, которые могут содержать любой тип данных.</span><span class="sxs-lookup"><span data-stu-id="4976b-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="4976b-104">Visual Basic поддерживает перегрузку, однако и это делает `Any` устаревший тип данных.</span><span class="sxs-lookup"><span data-stu-id="4976b-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="4976b-105">**Идентификатор ошибки:** BC30828</span><span class="sxs-lookup"><span data-stu-id="4976b-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4976b-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4976b-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="4976b-107">Объявите параметры конкретного типа, который вы хотите использовать; Например.</span><span class="sxs-lookup"><span data-stu-id="4976b-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  <span data-ttu-id="4976b-108">Используйте <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут для указания `As Any` при `Void*` ожидается в вызываемой процедуре.</span><span class="sxs-lookup"><span data-stu-id="4976b-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4976b-109">См. также</span><span class="sxs-lookup"><span data-stu-id="4976b-109">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="4976b-110">Пошаговое руководство. Вызов API-интерфейсов Windows</span><span class="sxs-lookup"><span data-stu-id="4976b-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="4976b-111">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="4976b-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="4976b-112">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="4976b-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
