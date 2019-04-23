---
title: Как выполнить Загрузка и выгрузка сборок (C#)
ms.date: 07/20/2015
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
ms.openlocfilehash: 52f7173efe497ab286c607db681f256983adc077
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342048"
---
# <a name="how-to-load-and-unload-assemblies-c"></a><span data-ttu-id="85d57-102">Как выполнить Загрузка и выгрузка сборок (C#)</span><span class="sxs-lookup"><span data-stu-id="85d57-102">How to: Load and Unload Assemblies (C#)</span></span>
<span data-ttu-id="85d57-103">Сборки, на которые ссылается программа, загружаются автоматически во время построения, но в текущий домен приложения можно также загрузить конкретные сборки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="85d57-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="85d57-104">Дополнительные сведения см. в разделе [Как Загрузка сборок в домен приложения](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="85d57-104">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
 <span data-ttu-id="85d57-105">Отдельную сборку нельзя выгрузить, не выгрузив все домены приложений, в которых она содержится.</span><span class="sxs-lookup"><span data-stu-id="85d57-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="85d57-106">Даже если сборка не входит в область, фактический файл сборки остается загруженным до тех пор, пока не будут выгружены домены приложений с этой сборкой.</span><span class="sxs-lookup"><span data-stu-id="85d57-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="85d57-107">Если необходимо выгрузить только часть сборок, создайте новый домен приложения, выполните код внутри этого домена, а затем выгрузите этот домен приложения.</span><span class="sxs-lookup"><span data-stu-id="85d57-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="85d57-108">Дополнительные сведения см. в разделе [Как Выгрузка домена приложения](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="85d57-108">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="85d57-109">Загрузка сборки в домен приложения</span><span class="sxs-lookup"><span data-stu-id="85d57-109">To load an assembly into an application domain</span></span>  
  
1. <span data-ttu-id="85d57-110">Используйте один из нескольких методов загрузки, содержащихся в классах <xref:System.AppDomain> и <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="85d57-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="85d57-111">Дополнительные сведения см. в разделе [Как Загрузка сборок в домен приложения](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="85d57-111">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="85d57-112">Выгрузка домена приложения</span><span class="sxs-lookup"><span data-stu-id="85d57-112">To unload an application domain</span></span>  
  
1. <span data-ttu-id="85d57-113">Отдельную сборку нельзя выгрузить, не выгрузив все домены приложений, в которых она содержится.</span><span class="sxs-lookup"><span data-stu-id="85d57-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="85d57-114">Используйте метод `Unload` из <xref:System.AppDomain> для выгрузки доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="85d57-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="85d57-115">Дополнительные сведения см. в разделе [Как Выгрузка домена приложения](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="85d57-115">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85d57-116">См. также</span><span class="sxs-lookup"><span data-stu-id="85d57-116">See also</span></span>

- [<span data-ttu-id="85d57-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="85d57-117">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="85d57-118">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="85d57-118">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="85d57-119">Практическое руководство. Загрузка сборок в домен приложения</span><span class="sxs-lookup"><span data-stu-id="85d57-119">How to: Load Assemblies into an Application Domain</span></span>](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
