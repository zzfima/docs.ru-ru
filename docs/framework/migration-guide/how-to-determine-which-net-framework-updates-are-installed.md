---
title: Практическое руководство. Определение установленных обновлений и исправлений безопасности платформы .NET Framework
description: Сведения об определении установленных на компьютере обновлений и исправлений безопасности платформы .NET Framework.
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6373def6859023377bf899f02d710c2ac6d83c44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33389604"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="e971b-103">Практическое руководство. Определение установленных обновлений и исправлений безопасности платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e971b-103">How to: Determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="e971b-104">В этой статье содержатся сведения об определении установленных на компьютере обновлений и исправлений безопасности платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e971b-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="e971b-105">Для использования всех методов, представленных в этой статье, требуется учетная запись с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="e971b-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="to-find-installed-updates-using-the-registry"></a><span data-ttu-id="e971b-106">Поиск установленных обновлений с помощью реестра</span><span class="sxs-lookup"><span data-stu-id="e971b-106">To find installed updates using the registry</span></span>

<span data-ttu-id="e971b-107">Установленные обновления и исправления безопасности для каждой версии .NET Framework на компьютере перечислены в реестре Windows.</span><span class="sxs-lookup"><span data-stu-id="e971b-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="e971b-108">Для просмотра этих сведений можно использовать редактор реестра (*regedit.exe*).</span><span class="sxs-lookup"><span data-stu-id="e971b-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="e971b-109">Откройте программу **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="e971b-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="e971b-110">В Windows 8 и более поздних версиях щелкните правой кнопкой мыши **Пуск** ![Эмблема Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), а затем выберите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e971b-110">In Windows 8 and later versions, right-click **Start** ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="e971b-111">В поле **Открыть** введите **regedit**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e971b-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="e971b-112">В редакторе реестра откройте следующий подраздел:</span><span class="sxs-lookup"><span data-stu-id="e971b-112">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     <span data-ttu-id="e971b-113">Установленные обновления перечислены в подразделах, соответствующих версии .NET Framework, к которой они относятся.</span><span class="sxs-lookup"><span data-stu-id="e971b-113">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="e971b-114">Каждому обновлению присваивается номер базы знаний Microsoft (KB).</span><span class="sxs-lookup"><span data-stu-id="e971b-114">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="e971b-115">В редакторе реестра версии .NET Framework и установленные обновления для каждой версии хранятся в разных подразделах.</span><span class="sxs-lookup"><span data-stu-id="e971b-115">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="e971b-116">Сведения об обнаружении номеров установленных версий см. в статье [Практическое руководство. Определение установленных версий .NET Framework](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="e971b-116">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a><span data-ttu-id="e971b-117">Поиск установленных обновлений путем запроса к реестру в коде</span><span class="sxs-lookup"><span data-stu-id="e971b-117">To find installed updates by querying the registry in code</span></span>

<span data-ttu-id="e971b-118">В следующем примере кода программным образом определяются обновления и исправления безопасности .NET Framework, установленные на компьютере:</span><span class="sxs-lookup"><span data-stu-id="e971b-118">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="e971b-119">Выходные данные этого примера выглядят примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e971b-119">The example produces an output that's similar to the following one:</span></span>

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

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a><span data-ttu-id="e971b-120">Поиск установленных обновлений путем запроса к реестру в PowerShell</span><span class="sxs-lookup"><span data-stu-id="e971b-120">To find installed updates by querying the registry in PowerShell</span></span>

<span data-ttu-id="e971b-121">В следующем примере кода показано определение установленных на компьютере обновлений и исправлений безопасности .NET Framework с помощью PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e971b-121">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

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

<span data-ttu-id="e971b-122">Выходные данные этого примера выглядят примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e971b-122">The example produces an output that's similar to the following one:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e971b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e971b-123">See also</span></span>

[<span data-ttu-id="e971b-124">Практическое руководство.Определение установленных версий платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e971b-124">How to: Determine which .NET Framework versions are installed</span></span>](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[<span data-ttu-id="e971b-125">Установка .NET Framework для разработчиков</span><span class="sxs-lookup"><span data-stu-id="e971b-125">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)  
[<span data-ttu-id="e971b-126">Версии и зависимости</span><span class="sxs-lookup"><span data-stu-id="e971b-126">Versions and dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
