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
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a><span data-ttu-id="c75c9-102">&#39; Как любой &#39; не поддерживается в &#39; Declare &#39; инструкции</span><span class="sxs-lookup"><span data-stu-id="c75c9-102">&#39;As Any&#39; is not supported in &#39;Declare&#39; statements</span></span>
<span data-ttu-id="c75c9-103">`Any` Использование типа данных с `Declare` операторы в Visual Basic 6.0 и более ранних версий, чтобы разрешить использование аргументов, которые могут содержать любой тип данных.</span><span class="sxs-lookup"><span data-stu-id="c75c9-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="c75c9-104">поддерживает перегрузку, однако и это делает `Any` устаревший тип данных.</span><span class="sxs-lookup"><span data-stu-id="c75c9-104"> supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="c75c9-105">**Идентификатор ошибки:** BC30828</span><span class="sxs-lookup"><span data-stu-id="c75c9-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c75c9-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c75c9-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="c75c9-107">Объявите параметры конкретного типа, который вы хотите использовать; Например.</span><span class="sxs-lookup"><span data-stu-id="c75c9-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  <span data-ttu-id="c75c9-108">Используйте <xref:System.Runtime.InteropServices.MarshalAsAttribute> атрибут для указания `As Any` при `Void*` ожидается в вызываемой процедуре.</span><span class="sxs-lookup"><span data-stu-id="c75c9-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c75c9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="c75c9-109">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="c75c9-110">Пошаговое руководство. Вызов API-интерфейсов Windows</span><span class="sxs-lookup"><span data-stu-id="c75c9-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="c75c9-111">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="c75c9-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="c75c9-112">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="c75c9-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
