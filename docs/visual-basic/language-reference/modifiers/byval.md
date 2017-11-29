---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c192cdb4ac43ad614fbfb663079c03ddc6c358c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="byval-visual-basic"></a><span data-ttu-id="ec438-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec438-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="ec438-103">Указывает, что аргумент передается таким образом, вызванная процедура или свойство не может изменить значение переменной, представляющей аргумент в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="ec438-103">Specifies that an argument is passed in such a way that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec438-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="ec438-104">Remarks</span></span>  
 <span data-ttu-id="ec438-105">Модификатор `ByVal` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="ec438-105">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ec438-106">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="ec438-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="ec438-107">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="ec438-107">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="ec438-108">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="ec438-108">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="ec438-109">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="ec438-109">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="ec438-110">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="ec438-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="ec438-111">Пример</span><span class="sxs-lookup"><span data-stu-id="ec438-111">Example</span></span>  
 <span data-ttu-id="ec438-112">В следующем примере показано использование `ByVal` механизм с ссылочным аргументом типа передачи параметров.</span><span class="sxs-lookup"><span data-stu-id="ec438-112">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="ec438-113">В примере, — аргумент `c1`, экземпляр класса `Class1`.</span><span class="sxs-lookup"><span data-stu-id="ec438-113">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="ec438-114">`ByVal`предотвращает изменение базовое значение аргумента ссылка кода в процедурах `c1`, но не защищает доступные поля и свойства `c1`.</span><span class="sxs-lookup"><span data-stu-id="ec438-114">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ec438-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ec438-115">See Also</span></span>  
 [<span data-ttu-id="ec438-116">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ec438-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="ec438-117">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="ec438-117">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
