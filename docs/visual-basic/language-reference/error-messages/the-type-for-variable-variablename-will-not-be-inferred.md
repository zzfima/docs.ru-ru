---
title: "Тип переменной &quot;&lt;variablename&gt;&quot; не будет определен, так как она привязана к полю во включающей области | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42110
- bc42110
dev_langs:
- VB
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
caps.latest.revision: 33
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 0f954fda84c9fd1a4af5315be2329de117e6d169
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---
# <a name="the-type-for-variable-39ltvariablenamegt39-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="77384-102">Тип переменной "&lt;variablename&gt;" не будет определен, так как она привязана к полю во включающей области</span><span class="sxs-lookup"><span data-stu-id="77384-102">The type for variable &#39;&lt;variablename&gt;&#39; will not be inferred because it is bound to a field in an enclosing scope</span></span>
<span data-ttu-id="77384-103">Тип переменной "\<variablename настроек" не будет определен, так как она привязана к полю во включающей области.</span><span class="sxs-lookup"><span data-stu-id="77384-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="77384-104">Либо измените имя "\<variablename настроек", или использовать полное доменное имя (например, «Me.variablename» или «MyBase.variablename»).</span><span class="sxs-lookup"><span data-stu-id="77384-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>  
  
 <span data-ttu-id="77384-105">Переменная управления циклом в коде имеет то же имя, как поле класса или других внешней области видимости.</span><span class="sxs-lookup"><span data-stu-id="77384-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="77384-106">Поскольку управляющая переменная используется без `As` предложения, он привязан к полю во включающей области, и компилятор не создает новую переменную и не вывести его тип.</span><span class="sxs-lookup"><span data-stu-id="77384-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>  
  
 <span data-ttu-id="77384-107">В следующем примере `Index`, управляющая переменная в `For` инструкции, привязан к `Index` в `Customer` класса.</span><span class="sxs-lookup"><span data-stu-id="77384-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="77384-108">Компилятор не создает новую переменную для переменной `Index` или вывести его тип.</span><span class="sxs-lookup"><span data-stu-id="77384-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>  
  
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
  
 <span data-ttu-id="77384-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="77384-109">By default, this message is a warning.</span></span> <span data-ttu-id="77384-110">Сведения о том, как скрыть предупреждения или как рассматривать предупреждения как ошибки в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="77384-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="77384-111">**Идентификатор ошибки:** BC42110</span><span class="sxs-lookup"><span data-stu-id="77384-111">**Error ID:** BC42110</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="77384-112">Устранение предупреждения</span><span class="sxs-lookup"><span data-stu-id="77384-112">To address this warning</span></span>  
  
-   <span data-ttu-id="77384-113">Сделайте локальной переменной цикла, изменив ее имя на идентификатор, который не является также именем поля класса.</span><span class="sxs-lookup"><span data-stu-id="77384-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   <span data-ttu-id="77384-114">Уточняется, что переменная управления циклом привязывается к полю класса с помощью префикса `Me.` на имя переменной.</span><span class="sxs-lookup"><span data-stu-id="77384-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   <span data-ttu-id="77384-115">Вместо того чтобы использовать вывод локального типа, используйте `As` предложение, чтобы указать тип для переменной цикла.</span><span class="sxs-lookup"><span data-stu-id="77384-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a><span data-ttu-id="77384-116">Пример</span><span class="sxs-lookup"><span data-stu-id="77384-116">Example</span></span>  
 <span data-ttu-id="77384-117">В следующем коде показано ранее примере с первого исправления на месте.</span><span class="sxs-lookup"><span data-stu-id="77384-117">The following code shows the earlier example with the first correction in place.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="77384-118">См. также</span><span class="sxs-lookup"><span data-stu-id="77384-118">See Also</span></span>  
 <span data-ttu-id="77384-119">[Оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="77384-119">[Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="77384-120"> [Для каждого... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="77384-120"> [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="77384-121"> [Для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="77384-121"> [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) </span></span>  
<span data-ttu-id="77384-122"> [Практическое руководство: ссылки на текущий экземпляр объекта](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span><span class="sxs-lookup"><span data-stu-id="77384-122"> [How to: Refer to the Current Instance of an Object](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span></span>  
<span data-ttu-id="77384-123"> [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="77384-123"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="77384-124"> [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span><span class="sxs-lookup"><span data-stu-id="77384-124"> [Me, My, MyBase, and MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span></span>

