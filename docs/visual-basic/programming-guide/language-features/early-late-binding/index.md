---
title: Раннее и позднее связывание
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
ms.openlocfilehash: bd70d8642c18e9bc2baba8128ec908c88e0477ce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345182"
---
# <a name="early-and-late-binding-visual-basic"></a><span data-ttu-id="2a34f-102">Раннее и позднее связывание (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a34f-102">Early and Late Binding (Visual Basic)</span></span>
<span data-ttu-id="2a34f-103">The Visual Basic compiler performs a process called `binding` when an object is assigned to an object variable.</span><span class="sxs-lookup"><span data-stu-id="2a34f-103">The Visual Basic compiler performs a process called `binding` when an object is assigned to an object variable.</span></span> <span data-ttu-id="2a34f-104">Объект является объектом *с ранним связыванием*, если он присвоен переменной, объявленной с определенным типом объекта.</span><span class="sxs-lookup"><span data-stu-id="2a34f-104">An object is *early bound* when it is assigned to a variable declared to be of a specific object type.</span></span> <span data-ttu-id="2a34f-105">Объекты с ранним связыванием позволяют компилятору выделять память и выполнять оптимизацию еще до запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="2a34f-105">Early bound objects allow the compiler to allocate memory and perform other optimizations before an application executes.</span></span> <span data-ttu-id="2a34f-106">Например, в следующем фрагменте кода объявляется переменная типа <xref:System.IO.FileStream>:</span><span class="sxs-lookup"><span data-stu-id="2a34f-106">For example, the following code fragment declares a variable to be of type <xref:System.IO.FileStream>:</span></span>  
  
 [!code-vb[VbVbalrOOP#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#90)]  
  
 <span data-ttu-id="2a34f-107">Так как <xref:System.IO.FileStream> — это тип конкретного объекта, для присвоенного переменной `FS` экземпляра происходит раннее связывание.</span><span class="sxs-lookup"><span data-stu-id="2a34f-107">Because <xref:System.IO.FileStream> is a specific object type, the instance assigned to `FS` is early bound.</span></span>  
  
 <span data-ttu-id="2a34f-108">И наоборот, объект является объектом *с поздним связыванием*, если он присваивается переменной, объявленной с типом `Object`.</span><span class="sxs-lookup"><span data-stu-id="2a34f-108">By contrast, an object is *late bound* when it is assigned to a variable declared to be of type `Object`.</span></span> <span data-ttu-id="2a34f-109">Объекты этого типа могут содержать ссылки на любой объект, но теряют многие преимущества раннего связывания.</span><span class="sxs-lookup"><span data-stu-id="2a34f-109">Objects of this type can hold references to any object, but lack many of the advantages of early-bound objects.</span></span> <span data-ttu-id="2a34f-110">Например, следующий фрагмент кода объявляет переменную объекта для хранения объекта, возвращаемого функцией `CreateObject`:</span><span class="sxs-lookup"><span data-stu-id="2a34f-110">For example, the following code fragment declares an object variable to hold an object returned by the `CreateObject` function:</span></span>  
  
 [!code-vb[VbVbalrOOP#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/LateBinding.vb#91)]  
  
## <a name="advantages-of-early-binding"></a><span data-ttu-id="2a34f-111">Преимущества раннего связывания</span><span class="sxs-lookup"><span data-stu-id="2a34f-111">Advantages of Early Binding</span></span>  
 <span data-ttu-id="2a34f-112">Раннее связывание объектов следует использовать везде, где это возможно, поскольку оно позволяет компилятору сделать важные оптимизации, повышающие эффективность приложений.</span><span class="sxs-lookup"><span data-stu-id="2a34f-112">You should use early-bound objects whenever possible, because they allow the compiler to make important optimizations that yield more efficient applications.</span></span> <span data-ttu-id="2a34f-113">Объекты с ранним связыванием работают значительно быстрее, чем объекты с поздним связыванием. Точное указание используемых объектов позволяет упростить чтение и обслуживание кода.</span><span class="sxs-lookup"><span data-stu-id="2a34f-113">Early-bound objects are significantly faster than late-bound objects and make your code easier to read and maintain by stating exactly what kind of objects are being used.</span></span> <span data-ttu-id="2a34f-114">Another advantage to early binding is that it enables useful features such as automatic code completion and Dynamic Help because the Visual Studio integrated development environment (IDE) can determine exactly what type of object you are working with as you edit the code.</span><span class="sxs-lookup"><span data-stu-id="2a34f-114">Another advantage to early binding is that it enables useful features such as automatic code completion and Dynamic Help because the Visual Studio integrated development environment (IDE) can determine exactly what type of object you are working with as you edit the code.</span></span> <span data-ttu-id="2a34f-115">Раннее связывание уменьшает количество и серьезность ошибок времени выполнения, так как позволяет компилятору фиксировать многие ошибки еще при компиляции программы.</span><span class="sxs-lookup"><span data-stu-id="2a34f-115">Early binding reduces the number and severity of run-time errors because it allows the compiler to report errors when a program is compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a34f-116">Позднее связывание применимо только для доступа к членам типа, объявленным как `Public`.</span><span class="sxs-lookup"><span data-stu-id="2a34f-116">Late binding can only be used to access type members that are declared as `Public`.</span></span> <span data-ttu-id="2a34f-117">Доступ к членам, объявленным как `Friend` или `Protected Friend`, приводит к ошибке времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="2a34f-117">Accessing members declared as `Friend` or `Protected Friend` results in a run-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a34f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2a34f-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>
- [<span data-ttu-id="2a34f-119">Время существования. Создание и уничтожение объектов</span><span class="sxs-lookup"><span data-stu-id="2a34f-119">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [<span data-ttu-id="2a34f-120">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="2a34f-120">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
