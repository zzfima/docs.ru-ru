---
title: Раннее и позднее связывание (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- objects [Visual Basic], late-bound
- objects [Visual Basic], early-bound
- objects [Visual Basic], late bound
- early binding [Visual Basic], Visual Basic compiler
- binding [Visual Basic], late and early
- objects [Visual Basic], early bound
- Visual Basic compiler, early and late binding
- late binding [Visual Basic]
- late binding [Visual Basic], Visual Basic compiler
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
ms.openlocfilehash: 8426899b0c0d3649f47cbd6ad5383dd3c95b9499
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647258"
---
# <a name="early-and-late-binding-visual-basic"></a><span data-ttu-id="dca50-102">Раннее и позднее связывание (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dca50-102">Early and Late Binding (Visual Basic)</span></span>
<span data-ttu-id="dca50-103">Компилятор Visual Basic выполняет процесс, называемый `binding` при присвоении переменной объекта.</span><span class="sxs-lookup"><span data-stu-id="dca50-103">The Visual Basic compiler performs a process called `binding` when an object is assigned to an object variable.</span></span> <span data-ttu-id="dca50-104">Объект является объектом *с ранним связыванием*, если он присвоен переменной, объявленной с определенным типом объекта.</span><span class="sxs-lookup"><span data-stu-id="dca50-104">An object is *early bound* when it is assigned to a variable declared to be of a specific object type.</span></span> <span data-ttu-id="dca50-105">Объекты с ранним связыванием позволяют компилятору выделять память и выполнять оптимизацию еще до запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="dca50-105">Early bound objects allow the compiler to allocate memory and perform other optimizations before an application executes.</span></span> <span data-ttu-id="dca50-106">Например, в следующем фрагменте кода объявляется переменная типа <xref:System.IO.FileStream>:</span><span class="sxs-lookup"><span data-stu-id="dca50-106">For example, the following code fragment declares a variable to be of type <xref:System.IO.FileStream>:</span></span>  
  
 [!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]  
  
 <span data-ttu-id="dca50-107">Так как <xref:System.IO.FileStream> — это тип конкретного объекта, для присвоенного переменной `FS` экземпляра происходит раннее связывание.</span><span class="sxs-lookup"><span data-stu-id="dca50-107">Because <xref:System.IO.FileStream> is a specific object type, the instance assigned to `FS` is early bound.</span></span>  
  
 <span data-ttu-id="dca50-108">И наоборот, объект является объектом *с поздним связыванием*, если он присваивается переменной, объявленной с типом `Object`.</span><span class="sxs-lookup"><span data-stu-id="dca50-108">By contrast, an object is *late bound* when it is assigned to a variable declared to be of type `Object`.</span></span> <span data-ttu-id="dca50-109">Объекты этого типа могут содержать ссылки на любой объект, но теряют многие преимущества раннего связывания.</span><span class="sxs-lookup"><span data-stu-id="dca50-109">Objects of this type can hold references to any object, but lack many of the advantages of early-bound objects.</span></span> <span data-ttu-id="dca50-110">Например, следующий фрагмент кода объявляет переменную объекта для хранения объекта, возвращаемого функцией `CreateObject`:</span><span class="sxs-lookup"><span data-stu-id="dca50-110">For example, the following code fragment declares an object variable to hold an object returned by the `CreateObject` function:</span></span>  
  
 [!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]  
  
## <a name="advantages-of-early-binding"></a><span data-ttu-id="dca50-111">Преимущества раннего связывания</span><span class="sxs-lookup"><span data-stu-id="dca50-111">Advantages of Early Binding</span></span>  
 <span data-ttu-id="dca50-112">Раннее связывание объектов следует использовать везде, где это возможно, поскольку оно позволяет компилятору сделать важные оптимизации, повышающие эффективность приложений.</span><span class="sxs-lookup"><span data-stu-id="dca50-112">You should use early-bound objects whenever possible, because they allow the compiler to make important optimizations that yield more efficient applications.</span></span> <span data-ttu-id="dca50-113">Объекты с ранним связыванием работают значительно быстрее, чем объекты с поздним связыванием. Точное указание используемых объектов позволяет упростить чтение и обслуживание кода.</span><span class="sxs-lookup"><span data-stu-id="dca50-113">Early-bound objects are significantly faster than late-bound objects and make your code easier to read and maintain by stating exactly what kind of objects are being used.</span></span> <span data-ttu-id="dca50-114">Является еще одним преимуществом использования для раннее связывание, что позволяет полезные возможности, такие как автоматическое завершение кода и Динамическая справка среды разработки Visual Studio (IDE) может точно определять тип объекта при редактировании код.</span><span class="sxs-lookup"><span data-stu-id="dca50-114">Another advantage to early binding is that it enables useful features such as automatic code completion and Dynamic Help because the Visual Studio integrated development environment (IDE) can determine exactly what type of object you are working with as you edit the code.</span></span> <span data-ttu-id="dca50-115">Раннее связывание уменьшает количество и серьезность ошибок времени выполнения, так как позволяет компилятору фиксировать многие ошибки еще при компиляции программы.</span><span class="sxs-lookup"><span data-stu-id="dca50-115">Early binding reduces the number and severity of run-time errors because it allows the compiler to report errors when a program is compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dca50-116">Позднее связывание применимо только для доступа к членам типа, объявленным как `Public`.</span><span class="sxs-lookup"><span data-stu-id="dca50-116">Late binding can only be used to access type members that are declared as `Public`.</span></span> <span data-ttu-id="dca50-117">Доступ к членам, объявленным как `Friend` или `Protected Friend`, приводит к ошибке времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="dca50-117">Accessing members declared as `Friend` or `Protected Friend` results in a run-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dca50-118">См. также</span><span class="sxs-lookup"><span data-stu-id="dca50-118">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>  
 [<span data-ttu-id="dca50-119">Время существования. Создание и уничтожение объектов</span><span class="sxs-lookup"><span data-stu-id="dca50-119">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [<span data-ttu-id="dca50-120">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="dca50-120">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
