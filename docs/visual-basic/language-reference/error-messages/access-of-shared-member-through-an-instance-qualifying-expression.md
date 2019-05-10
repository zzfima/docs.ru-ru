---
title: Доступ к общему члену через экземпляр; выражение уточнения не вычисляется
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 311f4c025072162e0cfb6b87587f8602d33fcd19
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646870"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a><span data-ttu-id="c76cb-102">Доступ к общему члену через экземпляр; выражение уточнения не вычисляется</span><span class="sxs-lookup"><span data-stu-id="c76cb-102">Access of shared member through an instance; qualifying expression will not be evaluated</span></span>
<span data-ttu-id="c76cb-103">Переменная экземпляра класса или структуры используется для доступа к `Shared` переменной, свойства, процедуры или события, определенного в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="c76cb-103">An instance variable of a class or structure is used to access a `Shared` variable, property, procedure, or event defined in that class or structure.</span></span> <span data-ttu-id="c76cb-104">Это предупреждение также может возникнуть, если переменная экземпляра используется для доступа к неявному общему члену класса или структуры, такие как константа перечисления, или вложенного класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="c76cb-104">This warning can also occur if an instance variable is used to access an implicitly shared member of a class or structure, such as a constant or enumeration, or a nested class or structure.</span></span>  
  
 <span data-ttu-id="c76cb-105">Совместное использование членов предназначена для создания только одной копии этого элемента и предоставления этой копии для каждого экземпляра класса или структуры, в котором она объявлена.</span><span class="sxs-lookup"><span data-stu-id="c76cb-105">The purpose of sharing a member is to create only a single copy of that member and make that single copy available to every instance of the class or structure in which it is declared.</span></span> <span data-ttu-id="c76cb-106">Он был совместим с этой цели, для доступа к `Shared` член через имя класса или структуры, а не через переменную, содержащую отдельный экземпляр этого класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="c76cb-106">It is consistent with this purpose to access a `Shared` member through the name of its class or structure, rather than through a variable that holds an individual instance of that class or structure.</span></span>  
  
 <span data-ttu-id="c76cb-107">Доступ к `Shared` элементу через переменную экземпляра может сделать код более трудным для понимания, поскольку этот член является `Shared`.</span><span class="sxs-lookup"><span data-stu-id="c76cb-107">Accessing a `Shared` member through an instance variable can make your code more difficult to understand by obscuring the fact that the member is `Shared`.</span></span> <span data-ttu-id="c76cb-108">Кроме того, если такой доступ является частью выражения, который выполняет другие действия, такие как `Function` процедуру, которая возвращает экземпляр общего члена, Visual Basic пропустит выражения и любые другие действия, в противном случае выполняет.</span><span class="sxs-lookup"><span data-stu-id="c76cb-108">Furthermore, if such access is part of an expression that performs other actions, such as a `Function` procedure that returns an instance of the shared member, Visual Basic bypasses the expression and any other actions it would otherwise perform.</span></span>  
  
 <span data-ttu-id="c76cb-109">Дополнительные сведения и пример см. в разделе [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="c76cb-109">For more information and an example, see [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
 <span data-ttu-id="c76cb-110">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="c76cb-110">By default, this message is a warning.</span></span> <span data-ttu-id="c76cb-111">Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c76cb-111">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="c76cb-112">**Идентификатор ошибки:** BC42025</span><span class="sxs-lookup"><span data-stu-id="c76cb-112">**Error ID:** BC42025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c76cb-113">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c76cb-113">To correct this error</span></span>  
  
- <span data-ttu-id="c76cb-114">Используйте имя класса или структуры, который определяет `Shared` члена к нему доступ, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c76cb-114">Use the name of the class or structure that defines the `Shared` member to access it, as shown in the following example.</span></span>  
  
```vb  
Public Class testClass  
    Public Shared Sub sayHello()  
        MsgBox("Hello")  
    End Sub  
End Class  
  
Module testModule  
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New testClass  
        tc.sayHello()  
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        testClass.sayHello()  
    End Sub  
End Module  
```  
  
> [!NOTE]
>  <span data-ttu-id="c76cb-115">Предупреждение для эффектов области Будьте в том случае, если два программных элемента имеют одинаковое имя.</span><span class="sxs-lookup"><span data-stu-id="c76cb-115">Be alert for the effects of scope when two programming elements have the same name.</span></span> <span data-ttu-id="c76cb-116">В предыдущем примере, если вы объявите экземпляр с помощью `Dim testClass as testClass = Nothing`, компилятор обрабатывает вызов `testClass.sayHello()` как доступа метода через имя класса и предупреждение не возникает.</span><span class="sxs-lookup"><span data-stu-id="c76cb-116">In the previous example, if you declare an instance by using `Dim testClass as testClass = Nothing`, the compiler treats a call to `testClass.sayHello()` as an access of the method through the class name, and no warning occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c76cb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c76cb-117">See also</span></span>

- [<span data-ttu-id="c76cb-118">Общие</span><span class="sxs-lookup"><span data-stu-id="c76cb-118">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="c76cb-119">Область, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c76cb-119">Scope in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
