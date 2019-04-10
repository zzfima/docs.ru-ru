---
title: "'As Any' не поддерживается в операторах Declare"
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: 3593f238c72cbcce911c72e42552d6a75188b628
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310698"
---
# <a name="as-any-is-not-supported-in-declare-statements"></a><span data-ttu-id="f40cd-102">'As Any' не поддерживается в операторах Declare</span><span class="sxs-lookup"><span data-stu-id="f40cd-102">'As Any' is not supported in 'Declare' statements</span></span>
<span data-ttu-id="f40cd-103">`Any` Использовался тип данных с помощью `Declare` операторов в Visual Basic 6.0 и более ранних версий, чтобы разрешить использование аргументов, которые могут содержать данные любого типа.</span><span class="sxs-lookup"><span data-stu-id="f40cd-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> <span data-ttu-id="f40cd-104">Visual Basic поддерживает перегрузку, тем не менее и это делает `Any` устаревший тип данных.</span><span class="sxs-lookup"><span data-stu-id="f40cd-104">Visual Basic supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="f40cd-105">**Идентификатор ошибки:** BC30828</span><span class="sxs-lookup"><span data-stu-id="f40cd-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f40cd-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f40cd-106">To correct this error</span></span>  
  
1. <span data-ttu-id="f40cd-107">Объявите параметры конкретного типа, который вы хотите использовать; Например.</span><span class="sxs-lookup"><span data-stu-id="f40cd-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#95)]  
  
2. <span data-ttu-id="f40cd-108">Используйте <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут для указания `As Any` при `Void*` ожидается вызываемой процедуры.</span><span class="sxs-lookup"><span data-stu-id="f40cd-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#96)]  
  
## <a name="see-also"></a><span data-ttu-id="f40cd-109">См. также</span><span class="sxs-lookup"><span data-stu-id="f40cd-109">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f40cd-110">Пошаговое руководство. Вызов Windows API</span><span class="sxs-lookup"><span data-stu-id="f40cd-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="f40cd-111">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="f40cd-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="f40cd-112">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="f40cd-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
