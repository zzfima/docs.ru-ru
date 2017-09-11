---
title: "Практическое руководство: загрузка и выгрузка сборок (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2e38be72bb58573b532fa42a569563df0be8301d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a><span data-ttu-id="3b739-102">Практическое руководство: загрузка и выгрузка сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b739-102">How to: Load and Unload Assemblies (Visual Basic)</span></span>
<span data-ttu-id="3b739-103">Сборки ссылается программа будет автоматически загружаться во время построения, но можно также загрузить конкретные сборки в текущий домен приложения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="3b739-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="3b739-104">Дополнительные сведения см. в разделе [Практическое руководство: загрузка сборки в домен приложения](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span><span class="sxs-lookup"><span data-stu-id="3b739-104">For more information, see [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span></span>  
  
 <span data-ttu-id="3b739-105">Там будет невозможно выгружать отдельные сборки без выгрузки всех доменов приложений, которые его содержат.</span><span class="sxs-lookup"><span data-stu-id="3b739-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="3b739-106">Даже если сборка выходит за пределы области, фактический файл сборки будет оставаться загруженными, пока не будут выгружены все домены приложений, которые его содержат.</span><span class="sxs-lookup"><span data-stu-id="3b739-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="3b739-107">Если вы хотите выгрузить только некоторые сборки, рассмотрите возможность создания нового домена приложения, выполните код внутри этого домена и затем выгрузите это домен приложения.</span><span class="sxs-lookup"><span data-stu-id="3b739-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="3b739-108">Дополнительные сведения см. в разделе [как: выгрузка домена приложения](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span><span class="sxs-lookup"><span data-stu-id="3b739-108">For more information, see [How to: Unload an Application Domain](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="3b739-109">Для загрузки сборки в домен приложения</span><span class="sxs-lookup"><span data-stu-id="3b739-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="3b739-110">Используйте один из нескольких методов загрузки, содержащихся в классы <xref:System.AppDomain>и <xref:System.Reflection>.</xref:System.Reflection> </xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="3b739-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="3b739-111">Дополнительные сведения см. в разделе [Практическое руководство: загрузка сборки в домен приложения](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span><span class="sxs-lookup"><span data-stu-id="3b739-111">For more information, see [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="3b739-112">Чтобы выгрузить домен приложения</span><span class="sxs-lookup"><span data-stu-id="3b739-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="3b739-113">Там будет невозможно выгружать отдельные сборки без выгрузки всех доменов приложений, которые его содержат.</span><span class="sxs-lookup"><span data-stu-id="3b739-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="3b739-114">Используйте `Unload` метод <xref:System.AppDomain>для выгрузки доменов приложений.</xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="3b739-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="3b739-115">Дополнительные сведения см. в разделе [как: выгрузка домена приложения](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span><span class="sxs-lookup"><span data-stu-id="3b739-115">For more information, see [How to: Unload an Application Domain](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b739-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3b739-116">See Also</span></span>  
 <span data-ttu-id="3b739-117">[Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="3b739-117">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="3b739-118"> [Сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="3b739-118"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="3b739-119"> [Практическое руководство: загрузка сборок в домен приложения](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)</span><span class="sxs-lookup"><span data-stu-id="3b739-119"> [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)</span></span>
