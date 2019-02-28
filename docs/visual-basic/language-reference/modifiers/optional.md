---
title: Optional (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: b55252e774e744b7318f480b264aa3f7fae9abfc
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969652"
---
# <a name="optional-visual-basic"></a><span data-ttu-id="30d6f-102">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30d6f-102">Optional (Visual Basic)</span></span>
<span data-ttu-id="30d6f-103">Указывает, что аргумент процедуры может быть пропущен при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="30d6f-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30d6f-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="30d6f-104">Remarks</span></span>  
 <span data-ttu-id="30d6f-105">Для каждого необязательного параметра как значение по умолчанию этого параметра необходимо указать константное выражение.</span><span class="sxs-lookup"><span data-stu-id="30d6f-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="30d6f-106">Если выражение, результатом которого является [ничего не](../../../visual-basic/language-reference/nothing.md), как значение параметра по умолчанию используется значение по умолчанию для типа данных значений.</span><span class="sxs-lookup"><span data-stu-id="30d6f-106">If the expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>  
  
 <span data-ttu-id="30d6f-107">Если список параметров содержит необязательный параметр, каждый параметр, что следующий за ним также должен быть необязательным.</span><span class="sxs-lookup"><span data-stu-id="30d6f-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>  
  
 <span data-ttu-id="30d6f-108">Модификатор `Optional` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="30d6f-108">The `Optional` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="30d6f-109">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="30d6f-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="30d6f-110">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="30d6f-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="30d6f-111">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="30d6f-111">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="30d6f-112">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="30d6f-112">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  <span data-ttu-id="30d6f-113">При вызове процедуры с или без необязательных параметров, можно передать аргументы по положению или по имени.</span><span class="sxs-lookup"><span data-stu-id="30d6f-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="30d6f-114">Дополнительные сведения см. в разделе [передача аргументов по позиции и по имени](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="30d6f-114">For more information, see [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30d6f-115">Можно также определить с помощью перегрузка процедуры с необязательными параметрами.</span><span class="sxs-lookup"><span data-stu-id="30d6f-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="30d6f-116">Если у вас есть один необязательный параметр, можно определить две перегруженные версии процедуры, принимающую параметр, а другой не.</span><span class="sxs-lookup"><span data-stu-id="30d6f-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="30d6f-117">Дополнительные сведения см. в разделе [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="30d6f-117">For more information, see [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="30d6f-118">Пример</span><span class="sxs-lookup"><span data-stu-id="30d6f-118">Example</span></span>  
 <span data-ttu-id="30d6f-119">В следующем примере определяется процедуру, которая принимает необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="30d6f-119">The following example defines a procedure that has an optional parameter.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="30d6f-120">Пример</span><span class="sxs-lookup"><span data-stu-id="30d6f-120">Example</span></span>  
 <span data-ttu-id="30d6f-121">Следующий пример демонстрирует вызов процедуры с аргументы, передаваемые по позиции и с аргументами, передаваемыми по имени.</span><span class="sxs-lookup"><span data-stu-id="30d6f-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="30d6f-122">Процедура имеет два необязательных параметра.</span><span class="sxs-lookup"><span data-stu-id="30d6f-122">The procedure has two optional parameters.</span></span>  
  
 [!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="30d6f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="30d6f-123">See also</span></span>
- [<span data-ttu-id="30d6f-124">Список параметров</span><span class="sxs-lookup"><span data-stu-id="30d6f-124">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)
- [<span data-ttu-id="30d6f-125">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="30d6f-125">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="30d6f-126">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="30d6f-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
