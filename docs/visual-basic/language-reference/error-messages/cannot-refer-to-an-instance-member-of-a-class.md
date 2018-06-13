---
title: Не удается обратиться к члену экземпляра класса из совместно используемого метода или совместно используемого инициализатора без явного указания экземпляра этого класса
ms.date: 07/20/2015
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
ms.openlocfilehash: 368539ed24d9819c8d1ddbbb9e3e0dff21d27c32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590187"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a><span data-ttu-id="73ce8-102">Не удается обратиться к члену экземпляра класса из совместно используемого метода или совместно используемого инициализатора без явного указания экземпляра этого класса</span><span class="sxs-lookup"><span data-stu-id="73ce8-102">Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class</span></span>
<span data-ttu-id="73ce8-103">Вы попытались ссылается на член, не являющийся общим класса из общей процедуры.</span><span class="sxs-lookup"><span data-stu-id="73ce8-103">You have tried to refer to a non-shared member of a class from within a shared procedure.</span></span> <span data-ttu-id="73ce8-104">Ниже приведен пример такой ситуации.</span><span class="sxs-lookup"><span data-stu-id="73ce8-104">The following example demonstrates such a situation.</span></span>  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="73ce8-105">В предыдущем примере оператор присваивания `x = 10` это сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="73ce8-105">In the preceding example, the assignment statement `x = 10` generates this error message.</span></span> <span data-ttu-id="73ce8-106">Это так, как общая процедура пытается получить доступ к переменной экземпляра.</span><span class="sxs-lookup"><span data-stu-id="73ce8-106">This is because a shared procedure is attempting to access an instance variable.</span></span>  
  
 <span data-ttu-id="73ce8-107">Переменная `x` является членом экземпляра, так как он не объявлен как [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="73ce8-107">The variable `x` is an instance member because it is not declared as [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="73ce8-108">Каждый экземпляр класса `sample` содержит собственные переменные `x`.</span><span class="sxs-lookup"><span data-stu-id="73ce8-108">Each instance of class `sample` contains its own individual variable `x`.</span></span> <span data-ttu-id="73ce8-109">Когда один экземпляр задает или изменяет значение `x`, не влияет на значение `x` в других экземплярах.</span><span class="sxs-lookup"><span data-stu-id="73ce8-109">When one instance sets or changes the value of `x`, it does not affect the value of `x` in any other instance.</span></span>  
  
 <span data-ttu-id="73ce8-110">Однако процедура `setX` — `Shared` среди всех экземпляров класса `sample`.</span><span class="sxs-lookup"><span data-stu-id="73ce8-110">However, the procedure `setX` is `Shared` among all instances of class `sample`.</span></span> <span data-ttu-id="73ce8-111">Это означает, что он не связан с какой-либо экземпляр класса, но вместо этого работает независимо от отдельных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="73ce8-111">This means it is not associated with any one instance of the class, but rather operates independently of individual instances.</span></span> <span data-ttu-id="73ce8-112">Так как она не связана с конкретным экземпляром `setX` не может получить доступ к переменной экземпляра.</span><span class="sxs-lookup"><span data-stu-id="73ce8-112">Because it has no connection with a particular instance, `setX` cannot access an instance variable.</span></span> <span data-ttu-id="73ce8-113">Она должна работать только с `Shared` переменных.</span><span class="sxs-lookup"><span data-stu-id="73ce8-113">It must operate only on `Shared` variables.</span></span> <span data-ttu-id="73ce8-114">Когда `setX` задает или изменяет значение общей переменной, это новое значение становится доступным всем экземплярам класса.</span><span class="sxs-lookup"><span data-stu-id="73ce8-114">When `setX` sets or changes the value of a shared variable, that new value is available to all instances of the class.</span></span>  
  
 <span data-ttu-id="73ce8-115">**Идентификатор ошибки:** BC30369</span><span class="sxs-lookup"><span data-stu-id="73ce8-115">**Error ID:** BC30369</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="73ce8-116">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="73ce8-116">To correct this error</span></span>  
  
1.  <span data-ttu-id="73ce8-117">Решите, будет ли элемент общим для всех экземпляров класса, то сохраняются отдельно для каждого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="73ce8-117">Decide whether you want the member to be shared among all instances of the class, or kept individual for each instance.</span></span>  
  
2.  <span data-ttu-id="73ce8-118">Если требуется одна копия элемента для всех экземпляров, добавьте `Shared` ключевое слово в объявлении члена.</span><span class="sxs-lookup"><span data-stu-id="73ce8-118">If you want a single copy of the member to be shared among all instances, add the `Shared` keyword to the member declaration.</span></span> <span data-ttu-id="73ce8-119">Сохранить `Shared` ключевое слово в объявлении процедуры.</span><span class="sxs-lookup"><span data-stu-id="73ce8-119">Retain the `Shared` keyword in the procedure declaration.</span></span>  
  
3.  <span data-ttu-id="73ce8-120">Если требуется, чтобы каждый экземпляр для отдельных копия элемента, не указывайте `Shared` для объявления члена.</span><span class="sxs-lookup"><span data-stu-id="73ce8-120">If you want each instance to have its own individual copy of the member, do not specify `Shared` for the member declaration.</span></span> <span data-ttu-id="73ce8-121">Удалить `Shared` ключевое слово из объявления процедуры.</span><span class="sxs-lookup"><span data-stu-id="73ce8-121">Remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73ce8-122">См. также</span><span class="sxs-lookup"><span data-stu-id="73ce8-122">See Also</span></span>  
 [<span data-ttu-id="73ce8-123">Общие</span><span class="sxs-lookup"><span data-stu-id="73ce8-123">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
