---
title: "Раннее и позднее связывание (Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- early binding
- objects [Visual Basic], late-bound
- objects [Visual Basic], early-bound
- objects [Visual Basic], late bound
- early binding, Visual Basic compiler
- binding, late and early
- objects [Visual Basic], early bound
- Visual Basic compiler, early and late binding
- late binding
- late binding, Visual Basic compiler
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 66a34580417fb8b4a814b237ec36ffe700b1b30a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="early-and-late-binding-visual-basic"></a><span data-ttu-id="2331f-102">Раннее и позднее связывание (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2331f-102">Early and Late Binding (Visual Basic)</span></span>
<span data-ttu-id="2331f-103">При присвоении переменной объекта компилятор [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] выполняет процесс, называемый связыванием (`binding`).</span><span class="sxs-lookup"><span data-stu-id="2331f-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler performs a process called `binding` when an object is assigned to an object variable.</span></span> <span data-ttu-id="2331f-104">Объект является объектом *с ранним связыванием*, если он присвоен переменной, объявленной с определенным типом объекта.</span><span class="sxs-lookup"><span data-stu-id="2331f-104">An object is *early bound* when it is assigned to a variable declared to be of a specific object type.</span></span> <span data-ttu-id="2331f-105">Объекты с ранним связыванием позволяют компилятору выделять память и выполнять оптимизацию еще до запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="2331f-105">Early bound objects allow the compiler to allocate memory and perform other optimizations before an application executes.</span></span> <span data-ttu-id="2331f-106">Например, в следующем фрагменте кода объявляется переменная типа <xref:System.IO.FileStream>:</span><span class="sxs-lookup"><span data-stu-id="2331f-106">For example, the following code fragment declares a variable to be of type <xref:System.IO.FileStream>:</span></span>  
  
 <span data-ttu-id="2331f-107">[!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2331f-107">[!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]</span></span>  
  
 <span data-ttu-id="2331f-108">Так как <xref:System.IO.FileStream> — это тип конкретного объекта, для присвоенного переменной `FS` экземпляра происходит раннее связывание.</span><span class="sxs-lookup"><span data-stu-id="2331f-108">Because <xref:System.IO.FileStream> is a specific object type, the instance assigned to `FS` is early bound.</span></span>  
  
 <span data-ttu-id="2331f-109">И наоборот, объект является объектом *с поздним связыванием*, если он присваивается переменной, объявленной с типом `Object`.</span><span class="sxs-lookup"><span data-stu-id="2331f-109">By contrast, an object is *late bound* when it is assigned to a variable declared to be of type `Object`.</span></span> <span data-ttu-id="2331f-110">Объекты этого типа могут содержать ссылки на любой объект, но теряют многие преимущества раннего связывания.</span><span class="sxs-lookup"><span data-stu-id="2331f-110">Objects of this type can hold references to any object, but lack many of the advantages of early-bound objects.</span></span> <span data-ttu-id="2331f-111">Например, следующий фрагмент кода объявляет переменную объекта для хранения объекта, возвращаемого функцией `CreateObject`:</span><span class="sxs-lookup"><span data-stu-id="2331f-111">For example, the following code fragment declares an object variable to hold an object returned by the `CreateObject` function:</span></span>  
  
 <span data-ttu-id="2331f-112">[!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2331f-112">[!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]</span></span>  
  
## <a name="advantages-of-early-binding"></a><span data-ttu-id="2331f-113">Преимущества раннего связывания</span><span class="sxs-lookup"><span data-stu-id="2331f-113">Advantages of Early Binding</span></span>  
 <span data-ttu-id="2331f-114">Раннее связывание объектов следует использовать везде, где это возможно, поскольку оно позволяет компилятору сделать важные оптимизации, повышающие эффективность приложений.</span><span class="sxs-lookup"><span data-stu-id="2331f-114">You should use early-bound objects whenever possible, because they allow the compiler to make important optimizations that yield more efficient applications.</span></span> <span data-ttu-id="2331f-115">Объекты с ранним связыванием работают значительно быстрее, чем объекты с поздним связыванием. Точное указание используемых объектов позволяет упростить чтение и обслуживание кода.</span><span class="sxs-lookup"><span data-stu-id="2331f-115">Early-bound objects are significantly faster than late-bound objects and make your code easier to read and maintain by stating exactly what kind of objects are being used.</span></span> <span data-ttu-id="2331f-116">Кроме того, раннее связывание позволяет использовать ряд дополнительных полезных возможностей, например автоматическое завершение кода и динамическую справку, поскольку интегрированная среда разработки (IDE) [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] может точно определить тип объекта при редактировании кода.</span><span class="sxs-lookup"><span data-stu-id="2331f-116">Another advantage to early binding is that it enables useful features such as automatic code completion and Dynamic Help because the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] integrated development environment (IDE) can determine exactly what type of object you are working with as you edit the code.</span></span> <span data-ttu-id="2331f-117">Раннее связывание уменьшает количество и серьезность ошибок времени выполнения, так как позволяет компилятору фиксировать многие ошибки еще при компиляции программы.</span><span class="sxs-lookup"><span data-stu-id="2331f-117">Early binding reduces the number and severity of run-time errors because it allows the compiler to report errors when a program is compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2331f-118">Позднее связывание применимо только для доступа к членам типа, объявленным как `Public`.</span><span class="sxs-lookup"><span data-stu-id="2331f-118">Late binding can only be used to access type members that are declared as `Public`.</span></span> <span data-ttu-id="2331f-119">Доступ к членам, объявленным как `Friend` или `Protected Friend`, приводит к ошибке времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="2331f-119">Accessing members declared as `Friend` or `Protected Friend` results in a run-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2331f-120">См. также</span><span class="sxs-lookup"><span data-stu-id="2331f-120">See Also</span></span>  
 <span data-ttu-id="2331f-121"><xref:Microsoft.VisualBasic.Interaction.CreateObject%2A></span><span class="sxs-lookup"><span data-stu-id="2331f-121"><xref:Microsoft.VisualBasic.Interaction.CreateObject%2A></span></span>   
 <span data-ttu-id="2331f-122">[Object Lifetime: How Objects Are Created and Destroyed (Visual Basic)](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  (Время существования, создание и уничтожение объектов (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="2331f-122">[Object Lifetime: How Objects Are Created and Destroyed](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md) </span></span>  
 [<span data-ttu-id="2331f-123">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="2331f-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)

