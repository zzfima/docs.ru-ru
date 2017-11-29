---
title: "Практическое руководство.Определение установленных обновлений платформы .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ba734dd3a9585b52b96cb2d27743da6190961126
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-determine-which-net-framework-updates-are-installed"></a><span data-ttu-id="124eb-102">Практическое руководство.Определение установленных обновлений платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="124eb-102">How to: Determine Which .NET Framework Updates Are Installed</span></span>
<span data-ttu-id="124eb-103">Установленные обновления для каждой версии .NET Framework на компьютере, перечислены в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="124eb-103">The installed updates for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="124eb-104">Для просмотра этих сведений можно использовать редактор реестра (regedit.exe).</span><span class="sxs-lookup"><span data-stu-id="124eb-104">You can use the Registry Editor (regedit.exe) to view this information.</span></span>  
  
 <span data-ttu-id="124eb-105">В редакторе реестра версии .NET Framework и установленные обновления для каждой версии хранятся в разных подразделах.</span><span class="sxs-lookup"><span data-stu-id="124eb-105">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="124eb-106">Сведения об обнаружении номеров установленных версий см. в статье [Практическое руководство. Определение установленных версий .NET Framework](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="124eb-106">For information about detecting the installed version numbers, see [How to: Determine Which .NET Framework Versions Are Installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span> <span data-ttu-id="124eb-107">Сведения об установке .NET Framework см. в разделе [Установка .NET Framework для разработчиков](../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="124eb-107">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
### <a name="to-find-installed-updates"></a><span data-ttu-id="124eb-108">Поиск установленных обновлений</span><span class="sxs-lookup"><span data-stu-id="124eb-108">To find installed updates</span></span>  
  
1.  <span data-ttu-id="124eb-109">Откройте программу **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="124eb-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="124eb-110">В Windows 8 и более поздних версиях откройте рабочий стол и введите имя.</span><span class="sxs-lookup"><span data-stu-id="124eb-110">In Windows 8 and higher open the Start screen and type the name.</span></span> <span data-ttu-id="124eb-111">В более ранних версиях Windows, в меню **Пуск** щелкните **Выполнить**, а затем в поле **Открыть** введите **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="124eb-111">In earlier versions of Windows, on the **Start** menu, choose **Run** and then, in the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="124eb-112">Для запуска regedit.exe необходимы учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="124eb-112">You must have administrative credentials to run regedit.exe.</span></span>  
  
2.  <span data-ttu-id="124eb-113">В редакторе реестра откройте следующий подраздел:</span><span class="sxs-lookup"><span data-stu-id="124eb-113">In the Registry Editor, open the following subkey:</span></span>  
  
     <span data-ttu-id="124eb-114">HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates</span><span class="sxs-lookup"><span data-stu-id="124eb-114">HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates</span></span>  
  
     <span data-ttu-id="124eb-115">Установленные обновления перечислены в подразделах, соответствующих версии .NET Framework, к которой они относятся.</span><span class="sxs-lookup"><span data-stu-id="124eb-115">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="124eb-116">Каждому обновлению присваивается номер базы знаний Microsoft (KB).</span><span class="sxs-lookup"><span data-stu-id="124eb-116">Each update is identified by a Knowledge Base (KB) number.</span></span>  
  
## <a name="example"></a><span data-ttu-id="124eb-117">Пример</span><span class="sxs-lookup"><span data-stu-id="124eb-117">Example</span></span>  
 <span data-ttu-id="124eb-118">В следующем примере кода программным образом определяются обновления .NET Framework, установленные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="124eb-118">The following code programmatically determines the .NET Framework updates that are installed on a computer.</span></span> <span data-ttu-id="124eb-119">Для запуска этого примера требуются права администратора.</span><span class="sxs-lookup"><span data-stu-id="124eb-119">You must have administrative credentials to run this example.</span></span>  
  
 [!code-csharp[ListUpdates#1](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs#1)]
 [!code-vb[ListUpdates#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb#1)]  
  
 <span data-ttu-id="124eb-120">Выходные данные этого примера выглядят примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="124eb-120">The example produces output that's similar to the following:</span></span>  
  
```  
Microsoft .NET Framework 3.5 SP1  
  KB953595  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB953595)  
  SP1  
    KB2657424  Security Update for Microsoft .NET Framework 3.5 SP1 (KB2657424)  
    KB958484  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB958484)  
    KB963707  Update for Microsoft .NET Framework 3.5 SP1 (KB963707)  
Microsoft .NET Framework 4 Client Profile  
  KB2160841  Security Update for Microsoft .NET Framework 4 Client Profile (KB2160841)  
  KB2446708  Security Update for Microsoft .NET Framework 4 Client Profile (KB2446708)  
  KB2468871  Update for Microsoft .NET Framework 4 Client Profile (KB2468871)  
  KB2478663  Security Update for Microsoft .NET Framework 4 Client Profile (KB2478663)  
  KB2518870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2518870)  
  KB2533523  Update for Microsoft .NET Framework 4 Client Profile (KB2533523)  
  KB2539636  Security Update for Microsoft .NET Framework 4 Client Profile (KB2539636)  
  KB2572078  Security Update for Microsoft .NET Framework 4 Client Profile (KB2572078)  
  KB2633870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2633870)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Client Profile (KB2656351)  
Microsoft .NET Framework 4 Extended  
  KB2416472  Security Update for Microsoft .NET Framework 4 Extended (KB2416472)  
  KB2468871  Update for Microsoft .NET Framework 4 Extended (KB2468871)  
  KB2487367  Security Update for Microsoft .NET Framework 4 Extended (KB2487367)  
  KB2533523  Update for Microsoft .NET Framework 4 Extended (KB2533523)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Extended (KB2656351)  
```  
  
## <a name="see-also"></a><span data-ttu-id="124eb-121">См. также</span><span class="sxs-lookup"><span data-stu-id="124eb-121">See also</span></span>

<span data-ttu-id="124eb-122">[Практическое руководство. Определение установленных версий платформы .NET Framework](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) </span><span class="sxs-lookup"><span data-stu-id="124eb-122">[How to: Determine Which .NET Framework Versions Are Installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) </span></span>  
<span data-ttu-id="124eb-123">[Установка .NET Framework](../../../docs/framework/install/guide-for-developers.md) </span><span class="sxs-lookup"><span data-stu-id="124eb-123">[Installing the .NET Framework](../../../docs/framework/install/guide-for-developers.md) </span></span>  
[<span data-ttu-id="124eb-124">Версии и зависимости</span><span class="sxs-lookup"><span data-stu-id="124eb-124">Versions and Dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
