---
title: Лямбда-выражения недопустимы в первом выражении оператора Select Case
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: e51ba4ad0910d0db2b927f84303e5c55515f4b84
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843457"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a><span data-ttu-id="58250-102">Лямбда-выражения недопустимы в первом выражении оператора Select Case</span><span class="sxs-lookup"><span data-stu-id="58250-102">Lambda expressions are not valid in the first expression of a 'Select Case' statement</span></span>
<span data-ttu-id="58250-103">Лямбда-выражения нельзя использовать для проверки выражения в `Select Case` инструкции.</span><span class="sxs-lookup"><span data-stu-id="58250-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="58250-104">Определения лямбда-выражений возвращают функции, а выражение проверки `Select Case` инструкция должна быть простой тип данных.</span><span class="sxs-lookup"><span data-stu-id="58250-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="58250-105">Следующий код вызывает эту ошибку:</span><span class="sxs-lookup"><span data-stu-id="58250-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="58250-106">**Идентификатор ошибки:** BC36635</span><span class="sxs-lookup"><span data-stu-id="58250-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="58250-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="58250-107">To correct this error</span></span>  
  
-   <span data-ttu-id="58250-108">Проверьте свой код, чтобы определить, подойдет ли вам другая условная конструкция, например оператор `If...Then...Else` .</span><span class="sxs-lookup"><span data-stu-id="58250-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
-   <span data-ttu-id="58250-109">Возможно, предполагалось вызывать функцию, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="58250-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="58250-110">См. также</span><span class="sxs-lookup"><span data-stu-id="58250-110">See also</span></span>

- [<span data-ttu-id="58250-111">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="58250-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="58250-112">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="58250-112">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="58250-113">Оператор Select...Case</span><span class="sxs-lookup"><span data-stu-id="58250-113">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
