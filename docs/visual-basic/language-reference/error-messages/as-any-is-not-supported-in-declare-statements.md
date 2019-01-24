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
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a><span data-ttu-id="038d1-102">&#39;Как какой-либо&#39; не поддерживается в &#39;Declare&#39; инструкций</span><span class="sxs-lookup"><span data-stu-id="038d1-102">&#39;As Any&#39; is not supported in &#39;Declare&#39; statements</span></span>
<span data-ttu-id="038d1-103">`Any` Использовался тип данных с помощью `Declare` операторов в Visual Basic 6.0 и более ранних версий, чтобы разрешить использование аргументов, которые могут содержать данные любого типа.</span><span class="sxs-lookup"><span data-stu-id="038d1-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="038d1-104">Visual Basic поддерживает перегрузку, тем не менее и это делает `Any` устаревший тип данных.</span><span class="sxs-lookup"><span data-stu-id="038d1-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="038d1-105">**Идентификатор ошибки:** BC30828</span><span class="sxs-lookup"><span data-stu-id="038d1-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="038d1-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="038d1-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="038d1-107">Объявите параметры конкретного типа, который вы хотите использовать; Например.</span><span class="sxs-lookup"><span data-stu-id="038d1-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  <span data-ttu-id="038d1-108">Используйте <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут для указания `As Any` при `Void*` ожидается вызываемой процедуры.</span><span class="sxs-lookup"><span data-stu-id="038d1-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="038d1-109">См. также</span><span class="sxs-lookup"><span data-stu-id="038d1-109">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="038d1-110">Пошаговое руководство: Вызов API Windows</span><span class="sxs-lookup"><span data-stu-id="038d1-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="038d1-111">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="038d1-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="038d1-112">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="038d1-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
