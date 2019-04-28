---
title: Первый операнд в двоичном выражении If должен поддерживать значение NULL или быть ссылочного типа
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 32ff0adca9d35e6b5439ae06be85414924dac2e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801300"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="e5817-102">Первый операнд в двоичном выражении If должен поддерживать значение NULL или быть ссылочного типа</span><span class="sxs-lookup"><span data-stu-id="e5817-102">First operand in a binary 'If' expression must be nullable or a reference type</span></span>
<span data-ttu-id="e5817-103">`If` Выражение может принимать два или три аргумента.</span><span class="sxs-lookup"><span data-stu-id="e5817-103">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="e5817-104">При отправке только два аргумента, первый аргумент должен быть ссылочным типом или типом, допускающий значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e5817-104">When you send only two arguments, the first argument must be a reference type or a nullable type.</span></span> <span data-ttu-id="e5817-105">Если первый аргумент принимает на любое другое, отличное от `Nothing`, возвращается его значение.</span><span class="sxs-lookup"><span data-stu-id="e5817-105">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="e5817-106">Если первый аргумент принимает значение `Nothing`, второй аргумент вычисляется и возвращается.</span><span class="sxs-lookup"><span data-stu-id="e5817-106">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>  
  
 <span data-ttu-id="e5817-107">Например, следующий код содержит два `If` выражения: с тремя аргументами и с двумя аргументами.</span><span class="sxs-lookup"><span data-stu-id="e5817-107">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="e5817-108">Выражения вычисления и возвращают одинаковое значение.</span><span class="sxs-lookup"><span data-stu-id="e5817-108">The expressions calculate and return the same value.</span></span>  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 <span data-ttu-id="e5817-109">Следующие выражения вызывают эту ошибку:</span><span class="sxs-lookup"><span data-stu-id="e5817-109">The following expressions cause this error:</span></span>  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 <span data-ttu-id="e5817-110">**Идентификатор ошибки:** BC33107</span><span class="sxs-lookup"><span data-stu-id="e5817-110">**Error ID:** BC33107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e5817-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e5817-111">To correct this error</span></span>  
  
- <span data-ttu-id="e5817-112">Если не удается изменить код таким образом, первый аргумент является ссылочным типом или ссылочным типом, следует преобразовать с тремя аргументами `If` выражения, или к `If...Then...Else` инструкции.</span><span class="sxs-lookup"><span data-stu-id="e5817-112">If you cannot change the code so that the first argument is a nullable type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5817-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e5817-113">See also</span></span>

- [<span data-ttu-id="e5817-114">Оператор If</span><span class="sxs-lookup"><span data-stu-id="e5817-114">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="e5817-115">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="e5817-115">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="e5817-116">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="e5817-116">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
