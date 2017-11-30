---
title: Optional (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3aa01c2c1ae731c8fe00fdee24521760db69e624
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="optional-visual-basic"></a><span data-ttu-id="cb101-102">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb101-102">Optional (Visual Basic)</span></span>
<span data-ttu-id="cb101-103">Указывает, что аргумент процедуры может быть пропущен при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="cb101-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb101-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb101-104">Remarks</span></span>  
 <span data-ttu-id="cb101-105">Для каждого необязательного параметра как значение по умолчанию этого параметра необходимо указать константное выражение.</span><span class="sxs-lookup"><span data-stu-id="cb101-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="cb101-106">Если выражение, результатом которого является [ничего](../../../visual-basic/language-reference/nothing.md), значение по умолчанию для типа данных значение используется как значение параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cb101-106">If the expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>  
  
 <span data-ttu-id="cb101-107">Если список параметров содержит дополнительный параметр, каждый параметр, следующий за ним также должен быть необязательным.</span><span class="sxs-lookup"><span data-stu-id="cb101-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>  
  
 <span data-ttu-id="cb101-108">Модификатор `Optional` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="cb101-108">The `Optional` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="cb101-109">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="cb101-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="cb101-110">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="cb101-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="cb101-111">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="cb101-111">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="cb101-112">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="cb101-112">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  <span data-ttu-id="cb101-113">При вызове процедуры с или без необязательных параметров, аргументы можно передать по положению или по имени.</span><span class="sxs-lookup"><span data-stu-id="cb101-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="cb101-114">Дополнительные сведения см. в разделе [передача аргументов по позиции и по имени](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="cb101-114">For more information, see [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb101-115">Можно также определить процедуры с необязательными параметрами с помощью перегрузки.</span><span class="sxs-lookup"><span data-stu-id="cb101-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="cb101-116">Если у вас есть один необязательный параметр, можно определить две перегруженные версии процедуры, принимающую параметр, а другой не.</span><span class="sxs-lookup"><span data-stu-id="cb101-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="cb101-117">Дополнительные сведения см. в разделе [перегрузка процедур](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="cb101-117">For more information, see [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb101-118">Пример</span><span class="sxs-lookup"><span data-stu-id="cb101-118">Example</span></span>  
 <span data-ttu-id="cb101-119">В следующем примере определяется процедуру, которая принимает необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="cb101-119">The following example defines a procedure that has an optional parameter.</span></span>  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a><span data-ttu-id="cb101-120">Пример</span><span class="sxs-lookup"><span data-stu-id="cb101-120">Example</span></span>  
 <span data-ttu-id="cb101-121">Следующий пример демонстрирует вызов процедуры с аргументы, передаваемые по позиции и с аргументами, передаваемыми по имени.</span><span class="sxs-lookup"><span data-stu-id="cb101-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="cb101-122">Процедура включает два необязательных параметра.</span><span class="sxs-lookup"><span data-stu-id="cb101-122">The procedure has two optional parameters.</span></span>  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="cb101-123">См. также</span><span class="sxs-lookup"><span data-stu-id="cb101-123">See Also</span></span>  
 [<span data-ttu-id="cb101-124">Список параметров</span><span class="sxs-lookup"><span data-stu-id="cb101-124">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="cb101-125">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="cb101-125">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [<span data-ttu-id="cb101-126">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="cb101-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
