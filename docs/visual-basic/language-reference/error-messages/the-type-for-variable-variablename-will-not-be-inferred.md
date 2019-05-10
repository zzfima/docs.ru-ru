---
title: Тип для переменной <variablename> не будет определен, так как она привязана к полю во включающей области
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: a595f38f6dd68b9c152bfa78ec0bebf36e173e17
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649970"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="5db7a-102">Тип для переменной "\<имя_переменной >" не будет определен, так как она привязана к полю во включающей области</span><span class="sxs-lookup"><span data-stu-id="5db7a-102">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope</span></span>
<span data-ttu-id="5db7a-103">Тип для переменной "\<имя_переменной >" не будет определен, так как она привязана к полю во включающей области.</span><span class="sxs-lookup"><span data-stu-id="5db7a-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="5db7a-104">Либо измените имя "\<имя_переменной >", или используйте полное доменное имя (например, «Me.variablename» или «MyBase.variablename»).</span><span class="sxs-lookup"><span data-stu-id="5db7a-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>  
  
 <span data-ttu-id="5db7a-105">Управляющая переменная цикла в коде имеет имя, как поле класса или других внешней области видимости.</span><span class="sxs-lookup"><span data-stu-id="5db7a-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="5db7a-106">Так как переменная управления используется без `As` предложение, он привязан к полю во включающей области, и компилятор не создает новую переменную для него и вывести его тип.</span><span class="sxs-lookup"><span data-stu-id="5db7a-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>  
  
 <span data-ttu-id="5db7a-107">В следующем примере `Index`, управляющая переменная в `For` инструкции, привязан к `Index` в `Customer` класса.</span><span class="sxs-lookup"><span data-stu-id="5db7a-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="5db7a-108">Компилятор не создает новую переменную для управляющей переменной `Index` или вывести его тип.</span><span class="sxs-lookup"><span data-stu-id="5db7a-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="5db7a-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="5db7a-109">By default, this message is a warning.</span></span> <span data-ttu-id="5db7a-110">Дополнительные сведения о том, как скрыть предупреждения или как рассматривать предупреждения как ошибки, см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="5db7a-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="5db7a-111">**Идентификатор ошибки:** BC42110</span><span class="sxs-lookup"><span data-stu-id="5db7a-111">**Error ID:** BC42110</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="5db7a-112">Устранение предупреждения</span><span class="sxs-lookup"><span data-stu-id="5db7a-112">To address this warning</span></span>  
  
- <span data-ttu-id="5db7a-113">Сделайте локальный управляющей переменной цикла, изменив его имя на идентификатор, который не совпадает с именем поля класса.</span><span class="sxs-lookup"><span data-stu-id="5db7a-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>  
  
    ```  
    For I = 1 To 10  
    ```  
  
- <span data-ttu-id="5db7a-114">Уточняется, что управляющей переменной цикла привязывается к полю класса предваряя `Me.` к имени переменной.</span><span class="sxs-lookup"><span data-stu-id="5db7a-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
- <span data-ttu-id="5db7a-115">Вместо того чтобы вывод локального типа, используйте `As` предложение, чтобы указать тип управляющей переменной цикла for.</span><span class="sxs-lookup"><span data-stu-id="5db7a-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a><span data-ttu-id="5db7a-116">Пример</span><span class="sxs-lookup"><span data-stu-id="5db7a-116">Example</span></span>  
 <span data-ttu-id="5db7a-117">В следующем коде показано приведенного выше, в результате первого исправления на месте.</span><span class="sxs-lookup"><span data-stu-id="5db7a-117">The following code shows the earlier example with the first correction in place.</span></span>  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="5db7a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5db7a-118">See also</span></span>

- [<span data-ttu-id="5db7a-119">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="5db7a-119">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="5db7a-120">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="5db7a-120">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="5db7a-121">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="5db7a-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="5db7a-122">Практическое руководство. Ссылка на текущий экземпляр объекта</span><span class="sxs-lookup"><span data-stu-id="5db7a-122">How to: Refer to the Current Instance of an Object</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="5db7a-123">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="5db7a-123">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="5db7a-124">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="5db7a-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
