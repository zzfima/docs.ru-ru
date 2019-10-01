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
ms.openlocfilehash: a2a5ab99ff68e6dce783a2fd986ee6e8c15ae858
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701165"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a><span data-ttu-id="f8722-102">Не удается обратиться к члену экземпляра класса из совместно используемого метода или совместно используемого инициализатора без явного указания экземпляра этого класса</span><span class="sxs-lookup"><span data-stu-id="f8722-102">Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class</span></span>
<span data-ttu-id="f8722-103">Предпринята попытка ссылки на член класса, не являющийся общим, в рамках общей процедуры.</span><span class="sxs-lookup"><span data-stu-id="f8722-103">You have tried to refer to a non-shared member of a class from within a shared procedure.</span></span> <span data-ttu-id="f8722-104">В следующем примере показана такая ситуация.</span><span class="sxs-lookup"><span data-stu-id="f8722-104">The following example demonstrates such a situation.</span></span>  
  
```vb  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="f8722-105">В предыдущем примере инструкция присваивания `x = 10` создает это сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="f8722-105">In the preceding example, the assignment statement `x = 10` generates this error message.</span></span> <span data-ttu-id="f8722-106">Это связано с тем, что общая процедура пытается получить доступ к переменной экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f8722-106">This is because a shared procedure is attempting to access an instance variable.</span></span>  
  
 <span data-ttu-id="f8722-107">Переменная `x` является членом экземпляра, так как она не объявлена как [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="f8722-107">The variable `x` is an instance member because it is not declared as [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="f8722-108">Каждый экземпляр класса `sample` содержит собственную отдельную переменную `x`.</span><span class="sxs-lookup"><span data-stu-id="f8722-108">Each instance of class `sample` contains its own individual variable `x`.</span></span> <span data-ttu-id="f8722-109">Когда один экземпляр задает или изменяет значение `x`, оно не влияет на значение `x` в любом другом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="f8722-109">When one instance sets or changes the value of `x`, it does not affect the value of `x` in any other instance.</span></span>  
  
 <span data-ttu-id="f8722-110">Однако процедура `setX` `Shared` между всеми экземплярами класса `sample`.</span><span class="sxs-lookup"><span data-stu-id="f8722-110">However, the procedure `setX` is `Shared` among all instances of class `sample`.</span></span> <span data-ttu-id="f8722-111">Это означает, что он не связан с каким-либо экземпляром класса, а работает независимо от отдельных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="f8722-111">This means it is not associated with any one instance of the class, but rather operates independently of individual instances.</span></span> <span data-ttu-id="f8722-112">Так как он не имеет соединения с определенным экземпляром, `setX` не может получить доступ к переменной экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f8722-112">Because it has no connection with a particular instance, `setX` cannot access an instance variable.</span></span> <span data-ttu-id="f8722-113">Он должен обрабатывать только переменные `Shared`.</span><span class="sxs-lookup"><span data-stu-id="f8722-113">It must operate only on `Shared` variables.</span></span> <span data-ttu-id="f8722-114">Если `setX` задает или изменяет значение общей переменной, это новое значение доступно для всех экземпляров класса.</span><span class="sxs-lookup"><span data-stu-id="f8722-114">When `setX` sets or changes the value of a shared variable, that new value is available to all instances of the class.</span></span>  
  
 <span data-ttu-id="f8722-115">**Идентификатор ошибки:** BC30369</span><span class="sxs-lookup"><span data-stu-id="f8722-115">**Error ID:** BC30369</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f8722-116">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f8722-116">To correct this error</span></span>  
  
1. <span data-ttu-id="f8722-117">Решите, должен ли элемент быть общим для всех экземпляров класса или сохранен отдельно для каждого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f8722-117">Decide whether you want the member to be shared among all instances of the class, or kept individual for each instance.</span></span>  
  
2. <span data-ttu-id="f8722-118">Если требуется, чтобы одна копия члена была общей для всех экземпляров, добавьте к объявлению члена ключевое слово `Shared`.</span><span class="sxs-lookup"><span data-stu-id="f8722-118">If you want a single copy of the member to be shared among all instances, add the `Shared` keyword to the member declaration.</span></span> <span data-ttu-id="f8722-119">В объявлении процедуры Оставьте ключевое слово `Shared`.</span><span class="sxs-lookup"><span data-stu-id="f8722-119">Retain the `Shared` keyword in the procedure declaration.</span></span>  
  
3. <span data-ttu-id="f8722-120">Если требуется, чтобы каждый экземпляр имел собственную отдельную копию элемента, не указывайте `Shared` для объявления члена.</span><span class="sxs-lookup"><span data-stu-id="f8722-120">If you want each instance to have its own individual copy of the member, do not specify `Shared` for the member declaration.</span></span> <span data-ttu-id="f8722-121">Удалите ключевое слово `Shared` из объявления процедуры.</span><span class="sxs-lookup"><span data-stu-id="f8722-121">Remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8722-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f8722-122">See also</span></span>

- [<span data-ttu-id="f8722-123">Общие</span><span class="sxs-lookup"><span data-stu-id="f8722-123">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
