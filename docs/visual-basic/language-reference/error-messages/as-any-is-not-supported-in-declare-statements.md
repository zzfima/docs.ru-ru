---
title: "'As Any' не поддерживается в операторах Declare"
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: b3fb3f208f3396f454388ec0c10406815fa957d8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974800"
---
# <a name="as-any-is-not-supported-in-declare-statements"></a><span data-ttu-id="eff83-102">'As Any' не поддерживается в операторах Declare</span><span class="sxs-lookup"><span data-stu-id="eff83-102">'As Any' is not supported in 'Declare' statements</span></span>
<span data-ttu-id="eff83-103">`Any` Использовался тип данных с помощью `Declare` операторов в Visual Basic 6.0 и более ранних версий, чтобы разрешить использование аргументов, которые могут содержать данные любого типа.</span><span class="sxs-lookup"><span data-stu-id="eff83-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="eff83-104">Visual Basic поддерживает перегрузку, тем не менее и это делает `Any` устаревший тип данных.</span><span class="sxs-lookup"><span data-stu-id="eff83-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="eff83-105">**Идентификатор ошибки:** BC30828</span><span class="sxs-lookup"><span data-stu-id="eff83-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eff83-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="eff83-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="eff83-107">Объявите параметры конкретного типа, который вы хотите использовать; Например.</span><span class="sxs-lookup"><span data-stu-id="eff83-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#95)]  
  
2.  <span data-ttu-id="eff83-108">Используйте <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут для указания `As Any` при `Void*` ожидается вызываемой процедуры.</span><span class="sxs-lookup"><span data-stu-id="eff83-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#96)]  
  
## <a name="see-also"></a><span data-ttu-id="eff83-109">См. также</span><span class="sxs-lookup"><span data-stu-id="eff83-109">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="eff83-110">Пошаговое руководство: Вызов API Windows</span><span class="sxs-lookup"><span data-stu-id="eff83-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="eff83-111">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="eff83-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="eff83-112">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="eff83-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
