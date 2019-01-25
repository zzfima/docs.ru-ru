---
title: Первый операнд в двоичном файле &#39;Если&#39; выражения должен допускать значение NULL или ссылочный тип
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 85094ba6d6a44bf2e6cc4fba7946598c286a08a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668279"
---
# <a name="first-operand-in-a-binary-39if39-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="6f9a9-102">Первый операнд в двоичном файле &#39;Если&#39; выражения должен допускать значение NULL или ссылочный тип</span><span class="sxs-lookup"><span data-stu-id="6f9a9-102">First operand in a binary &#39;If&#39; expression must be nullable or a reference type</span></span>
<span data-ttu-id="6f9a9-103">`If` Выражение может принимать два или три аргумента.</span><span class="sxs-lookup"><span data-stu-id="6f9a9-103">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="6f9a9-104">При отправке только два аргумента, первый аргумент должен быть ссылочным типом или типом, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="6f9a9-104">When you send only two arguments, the first argument must be a reference type or a nullable type.</span></span> <span data-ttu-id="6f9a9-105">Если первый аргумент принимает на любое другое, отличное от `Nothing`, возвращается его значение.</span><span class="sxs-lookup"><span data-stu-id="6f9a9-105">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="6f9a9-106">Если первый аргумент принимает значение `Nothing`, второй аргумент вычисляется и возвращается.</span><span class="sxs-lookup"><span data-stu-id="6f9a9-106">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>  
  
 <span data-ttu-id="6f9a9-107">Например, следующий код содержит два `If` выражения: с тремя аргументами и с двумя аргументами.</span><span class="sxs-lookup"><span data-stu-id="6f9a9-107">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="6f9a9-108">Выражения вычисления и возвращают одинаковое значение.</span><span class="sxs-lookup"><span data-stu-id="6f9a9-108">The expressions calculate and return the same value.</span></span>  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 <span data-ttu-id="6f9a9-109">Следующие выражения вызывают эту ошибку:</span><span class="sxs-lookup"><span data-stu-id="6f9a9-109">The following expressions cause this error:</span></span>  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 <span data-ttu-id="6f9a9-110">**Идентификатор ошибки:** BC33107</span><span class="sxs-lookup"><span data-stu-id="6f9a9-110">**Error ID:** BC33107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6f9a9-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6f9a9-111">To correct this error</span></span>  
  
-   <span data-ttu-id="6f9a9-112">Если не удается изменить код таким образом, первый аргумент является ссылочным типом или ссылочным типом, следует преобразовать с тремя аргументами `If` выражения, или к `If...Then...Else` инструкции.</span><span class="sxs-lookup"><span data-stu-id="6f9a9-112">If you cannot change the code so that the first argument is a nullable type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f9a9-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6f9a9-113">See also</span></span>
- [<span data-ttu-id="6f9a9-114">Оператор If</span><span class="sxs-lookup"><span data-stu-id="6f9a9-114">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="6f9a9-115">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="6f9a9-115">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="6f9a9-116">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="6f9a9-116">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
