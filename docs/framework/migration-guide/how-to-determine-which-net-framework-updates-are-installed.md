---
title: "Практическое руководство. Определение установленных обновлений и исправлений безопасности платформы .NET Framework"
description: "Сведения об определении установленных на компьютере обновлений и исправлений безопасности платформы .NET Framework."
ms.date: 11/27/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9ff10928b87834f9b8e74e269082919f49497023
ms.sourcegitcommit: 39b65a49271e082add68cb737b48fdbe09d24718
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/30/2017
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="481b7-103">Практическое руководство. Определение установленных обновлений и исправлений безопасности платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="481b7-103">How to: Determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="481b7-104">В этой статье содержатся сведения об определении установленных на компьютере обновлений и исправлений безопасности платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="481b7-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="481b7-105">Для использования всех методов, представленных в этой статье, требуется учетная запись с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="481b7-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="to-find-installed-updates-using-the-registry"></a><span data-ttu-id="481b7-106">Поиск установленных обновлений с помощью реестра</span><span class="sxs-lookup"><span data-stu-id="481b7-106">To find installed updates using the registry</span></span>

<span data-ttu-id="481b7-107">Установленные обновления и исправления безопасности для каждой версии .NET Framework на компьютере перечислены в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="481b7-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="481b7-108">Для просмотра этих сведений можно использовать редактор реестра (*regedit.exe*).</span><span class="sxs-lookup"><span data-stu-id="481b7-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="481b7-109">Откройте программу **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="481b7-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="481b7-110">В Windows 8 и более поздних версиях щелкните правой кнопкой мыши **Пуск** ![Эмблема Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), а затем выберите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="481b7-110">In Windows 8 and later versions, right-click **Start** ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="481b7-111">В поле **Открыть** введите **regedit**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="481b7-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="481b7-112">В редакторе реестра откройте следующий подраздел:</span><span class="sxs-lookup"><span data-stu-id="481b7-112">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     <span data-ttu-id="481b7-113">Установленные обновления перечислены в подразделах, соответствующих версии .NET Framework, к которой они относятся.</span><span class="sxs-lookup"><span data-stu-id="481b7-113">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="481b7-114">Каждому обновлению присваивается номер базы знаний Microsoft (KB).</span><span class="sxs-lookup"><span data-stu-id="481b7-114">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="481b7-115">В редакторе реестра версии .NET Framework и установленные обновления для каждой версии хранятся в разных подразделах.</span><span class="sxs-lookup"><span data-stu-id="481b7-115">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="481b7-116">Сведения об обнаружении номеров установленных версий см. в статье [Практическое руководство. Определение установленных версий .NET Framework](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="481b7-116">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a><span data-ttu-id="481b7-117">Поиск установленных обновлений путем запроса к реестру в коде</span><span class="sxs-lookup"><span data-stu-id="481b7-117">To find installed updates by querying the registry in code</span></span>

<span data-ttu-id="481b7-118">В следующем примере кода программным образом определяются обновления и исправления безопасности .NET Framework, установленные на компьютере:</span><span class="sxs-lookup"><span data-stu-id="481b7-118">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="481b7-119">Выходные данные этого примера выглядят примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="481b7-119">The example produces an output that's similar to the following one:</span></span>

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a><span data-ttu-id="481b7-120">Поиск установленных обновлений путем запроса к реестру в PowerShell</span><span class="sxs-lookup"><span data-stu-id="481b7-120">To find installed updates by querying the registry in PowerShell</span></span>

<span data-ttu-id="481b7-121">В следующем примере кода показано определение установленных на компьютере обновлений и исправлений безопасности .NET Framework с помощью PowerShell:</span><span class="sxs-lookup"><span data-stu-id="481b7-121">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

```powershell
$DotNetVersions = Get-ChildItem HKLM:\SOFTWARE\WOW6432Node\Microsoft\Updates | Where-Object {$_.name -like
 "*.NET Framework*"}

ForEach($Version in $DotNetVersions){
    
   $Updates = Get-ChildItem $Version.PSPath
    $Version.PSChildName
    ForEach ($Update in $Updates){
       $Update.PSChildName
       }
}
```

<span data-ttu-id="481b7-122">Выходные данные этого примера выглядят примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="481b7-122">The example produces an output that's similar to the following one:</span></span>

```console
Microsoft .NET Framework 4 Client Profile
KB2468871
KB2468871v2
KB2478063
KB2533523
KB2544514
KB2600211
KB2600217
Microsoft .NET Framework 4 Extended
KB2468871
KB2468871v2
KB2478063
KB2533523
KB2544514
KB2600211
KB2600217
```

## <a name="see-also"></a><span data-ttu-id="481b7-123">См. также</span><span class="sxs-lookup"><span data-stu-id="481b7-123">See also</span></span>

[<span data-ttu-id="481b7-124">Практическое руководство.Определение установленных версий платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="481b7-124">How to: Determine which .NET Framework versions are installed</span></span>](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[<span data-ttu-id="481b7-125">Установка .NET Framework для разработчиков</span><span class="sxs-lookup"><span data-stu-id="481b7-125">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)  
[<span data-ttu-id="481b7-126">Версии и зависимости</span><span class="sxs-lookup"><span data-stu-id="481b7-126">Versions and dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
