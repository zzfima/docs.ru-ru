---
title: "глобальный кэш сборок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache)
- ACLs [.NET Framework]
- global assembly cache
- cache [.NET Framework], global assembly cache
- global assembly cache, about
- access control lists [.NET Framework]
ms.assetid: cf5eacd0-d3ec-4879-b6da-5fd5e4372202
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9ca51a06e6e7ec89576facf3a70c789325fd893c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="global-assembly-cache"></a><span data-ttu-id="d41cc-102">глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="d41cc-102">Global Assembly Cache</span></span>
<span data-ttu-id="d41cc-103">На каждом компьютере с установленной средой CLR имеется кэш кода на уровне компьютера, называемый глобальным кэшем сборок.</span><span class="sxs-lookup"><span data-stu-id="d41cc-103">Each computer where the common language runtime is installed has a machine-wide code cache called the global assembly cache.</span></span> <span data-ttu-id="d41cc-104">В глобальном кэше сборок сохраняются сборки, специально предназначенные для совместного использования на компьютере несколькими приложениями.</span><span class="sxs-lookup"><span data-stu-id="d41cc-104">The global assembly cache stores assemblies specifically designated to be shared by several applications on the computer.</span></span>  
  
 <span data-ttu-id="d41cc-105">Организовывать совместное использование сборок путем установки их в глобальный кэш следует только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="d41cc-105">You should share assemblies by installing them into the global assembly cache only when you need to.</span></span> <span data-ttu-id="d41cc-106">Как правило, зависимости между сборками следует сохранять закрытыми, а сами сборки нужно размещать в папке приложения, если они не предназначены для совместного использования.</span><span class="sxs-lookup"><span data-stu-id="d41cc-106">As a general guideline, keep assembly dependencies private, and locate assemblies in the application directory unless sharing an assembly is explicitly required.</span></span> <span data-ttu-id="d41cc-107">Кроме того, не обязательно устанавливать сборки в глобальный кэш сборок для доступа к ним из COM-взаимодействия или из неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="d41cc-107">In addition, it is not necessary to install assemblies into the global assembly cache to make them accessible to COM interop or unmanaged code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d41cc-108">Существуют случаи, в которых явно не требуется установка сборки в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="d41cc-108">There are scenarios where you explicitly do not want to install an assembly into the global assembly cache.</span></span> <span data-ttu-id="d41cc-109">Если одна из составляющих приложения сборок помещается в глобальный кэш сборок, то после этого нельзя будет скопировать или установить приложение с помощью команды **xcopy** путем копирования каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="d41cc-109">If you place one of the assemblies that make up an application in the global assembly cache, you can no longer replicate or install the application by using the **xcopy** command to copy the application directory.</span></span> <span data-ttu-id="d41cc-110">Для этого также потребуется переместить сборку в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="d41cc-110">You must move the assembly in the global assembly cache as well.</span></span>  
  
 <span data-ttu-id="d41cc-111">Существует два способа развертывания сборки в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="d41cc-111">There are two ways to deploy an assembly into the global assembly cache:</span></span>  
  
-   <span data-ttu-id="d41cc-112">Использование программы установки, предназначенной для работы с глобальным кэшем сборок.</span><span class="sxs-lookup"><span data-stu-id="d41cc-112">Use an installer designed to work with the global assembly cache.</span></span> <span data-ttu-id="d41cc-113">Данный подход является предпочтительным при установке сборок в глобальный кэш.</span><span class="sxs-lookup"><span data-stu-id="d41cc-113">This is the preferred option for installing assemblies into the global assembly cache.</span></span>  
  
-   <span data-ttu-id="d41cc-114">Использование инструмента разработчика под названием [средство глобального кэша сборок (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), предоставляемого в [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d41cc-114">Use a developer tool called the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), provided by the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d41cc-115">В сценариях развертывания для установки сборок в глобальный кэш используйте установщик Windows.</span><span class="sxs-lookup"><span data-stu-id="d41cc-115">In deployment scenarios, use Windows Installer to install assemblies into the global assembly cache.</span></span> <span data-ttu-id="d41cc-116">Средство глобального кэша сборок используйте только при разработке, поскольку оно не обеспечивает подсчет ссылок на сборку и другие возможности, предоставляемые при использовании установщика Windows.</span><span class="sxs-lookup"><span data-stu-id="d41cc-116">Use the Global Assembly Cache tool only in development scenarios, because it does not provide assembly reference counting and other features provided when using the Windows Installer.</span></span>  
  
 <span data-ttu-id="d41cc-117">Начиная с .NET Framework 4 расположение глобального кэша сборок по умолчанию — **%windir%\Microsoft.NET\assembly**.</span><span class="sxs-lookup"><span data-stu-id="d41cc-117">Starting with the .NET Framework 4, the default location for the global assembly cache is **%windir%\Microsoft.NET\assembly**.</span></span> <span data-ttu-id="d41cc-118">В более ранних версиях платформы .NET Framework расположение по умолчанию — **%windir%\assembly**.</span><span class="sxs-lookup"><span data-stu-id="d41cc-118">In earlier versions of the .NET Framework, the default location is **%windir%\assembly**.</span></span>  
  
 <span data-ttu-id="d41cc-119">Администраторы часто защищают папку systemroot с помощью списка управления доступом, определяющего права на запись и выполнение.</span><span class="sxs-lookup"><span data-stu-id="d41cc-119">Administrators often protect the systemroot directory using an access control list (ACL) to control write and execute access.</span></span> <span data-ttu-id="d41cc-120">Поскольку глобальный кэш сборок устанавливается в подкаталоге каталога SystemRoot, для него наследуется этот список управления доступом.</span><span class="sxs-lookup"><span data-stu-id="d41cc-120">Because the global assembly cache is installed in a subdirectory of the systemroot directory, it inherits that directory's ACL.</span></span> <span data-ttu-id="d41cc-121">Рекомендуется разрешать удаление файлов из глобального кэша сборок только пользователям, имеющим права доступа администратора.</span><span class="sxs-lookup"><span data-stu-id="d41cc-121">It is recommended that only users with Administrator privileges be allowed to delete files from the global assembly cache.</span></span>  
  
 <span data-ttu-id="d41cc-122">Приложения, развернутые в глобальном кэше сборок, должны иметь строгие имена.</span><span class="sxs-lookup"><span data-stu-id="d41cc-122">Assemblies deployed in the global assembly cache must have a strong name.</span></span> <span data-ttu-id="d41cc-123">При добавлении сборки в глобальный кэш сборок выполняется проверка целостности всех входящих в сборку файлов.</span><span class="sxs-lookup"><span data-stu-id="d41cc-123">When an assembly is added to the global assembly cache, integrity checks are performed on all files that make up the assembly.</span></span> <span data-ttu-id="d41cc-124">Кэш выполняет такую проверку целостности, чтобы гарантировать, что сборка не была изменена (например, если файл был изменен, но изменения не были отражены в манифесте сборки).</span><span class="sxs-lookup"><span data-stu-id="d41cc-124">The cache performs these integrity checks to ensure that an assembly has not been tampered with, for example, when a file has changed but the manifest does not reflect the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d41cc-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d41cc-125">See Also</span></span>  
 [<span data-ttu-id="d41cc-126">Сборки в среде CLR</span><span class="sxs-lookup"><span data-stu-id="d41cc-126">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [<span data-ttu-id="d41cc-127">Работа со сборками и глобальным кэшем сборок</span><span class="sxs-lookup"><span data-stu-id="d41cc-127">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="d41cc-128">Сборки со строгими именами</span><span class="sxs-lookup"><span data-stu-id="d41cc-128">Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/strong-named-assemblies.md)
