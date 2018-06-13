---
title: Практическое руководство. Установка сборки в глобальный кэш сборок
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed6519cb6bb7006f62ef83cd6baf8f2e32a44d19
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744386"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="014cf-102">Практическое руководство. Установка сборки в глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="014cf-102">How to: Install an Assembly into the Global Assembly Cache</span></span>
<span data-ttu-id="014cf-103">Существует два способа установки сборки со строгим именем в глобальный кэш сборок:</span><span class="sxs-lookup"><span data-stu-id="014cf-103">There are two ways to install a strong-named assembly into the global assembly cache (GAC):</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="014cf-104">В кэш могут быть установлены только сборки со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="014cf-104">Only strong-named assemblies can be installed into the GAC.</span></span> <span data-ttu-id="014cf-105">Сведения о создании сборки со строгим именем см. в разделе [Практическое руководство. Подписание сборки строгим именем](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="014cf-105">For information about how to create a strong-named assembly, see [How to: Sign an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
-   <span data-ttu-id="014cf-106">С помощью [установщика Windows](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx).</span><span class="sxs-lookup"><span data-stu-id="014cf-106">Using [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx).</span></span>  
  
     <span data-ttu-id="014cf-107">Для этого в Visual Studio 2012 и Visual Studio 2013 создается проект InstallShield Limited.</span><span class="sxs-lookup"><span data-stu-id="014cf-107">You do this in Visual Studio 2012 and Visual Studio 2013 by creating an InstallShield Limited Edition Project.</span></span>  
  
     <span data-ttu-id="014cf-108">Данный подход является рекомендуемым, а также наиболее общим способом добавления сборок в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="014cf-108">This is the recommended and most common way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="014cf-109">Программа установки предоставляет возможность подсчета ссылок на сборки в глобальном кэше сборок и другие дополнительные возможности.</span><span class="sxs-lookup"><span data-stu-id="014cf-109">The installer provides reference counting of assemblies in the global assembly cache, plus other benefits.</span></span>  
  
-   <span data-ttu-id="014cf-110">С помощью [программы глобального кэша сборок (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span><span class="sxs-lookup"><span data-stu-id="014cf-110">Using the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span></span>  
  
     <span data-ttu-id="014cf-111">Эту программу можно использовать для добавления сборок со строгими именами в глобальный кэш сборок и для просмотра содержимого указанного кэша.</span><span class="sxs-lookup"><span data-stu-id="014cf-111">You can use Gacutil.exe to add strong-named assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="014cf-112">Программа Gacutil.exe предназначена только для использования в процессе разработки и не должна использоваться для установки рабочих сборок в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="014cf-112">Gacutil.exe is only for development purposes and should not be used to install production assemblies into the global assembly cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="014cf-113">В предыдущих версиях .NET Framework расширение оболочки Windows Shfusion.dll позволяло устанавливать сборки, перетаскивая их в проводнике.</span><span class="sxs-lookup"><span data-stu-id="014cf-113">In earlier versions of the .NET Framework, the Shfusion.dll Windows shell extension enabled you to install assemblies by dragging them in File Explorer.</span></span> <span data-ttu-id="014cf-114">Начиная с версии [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], расширение оболочки Shfusion.dll является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="014cf-114">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
### <a name="to-use-the-global-assembly-cache-tool-gacutilexe"></a><span data-ttu-id="014cf-115">Использование средства глобального кэша сборок (Gacutil.exe)</span><span class="sxs-lookup"><span data-stu-id="014cf-115">To use the Global Assembly Cache tool (Gacutil.exe)</span></span>  
  
1.  <span data-ttu-id="014cf-116">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="014cf-116">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="014cf-117">**gacutil -i** \<*имя сборки*></span><span class="sxs-lookup"><span data-stu-id="014cf-117">**gacutil -i** \<*assembly name*></span></span>  
  
     <span data-ttu-id="014cf-118">В этой команде *имя сборки* представляет собой имя сборки, устанавливаемой в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="014cf-118">In this command, *assembly name* is the name of the assembly to install in the global assembly cache.</span></span>  
  
 <span data-ttu-id="014cf-119">В следующем примере выполняется установка сборки с именем файла `hello.dll` в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="014cf-119">The following example installs an assembly with the file name `hello.dll` into the global assembly cache.</span></span>  
  
```  
gacutil -i hello.dll  
```  
  
 <span data-ttu-id="014cf-120">Дополнительные сведения см. в разделе [Средство глобального кэша сборок (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span><span class="sxs-lookup"><span data-stu-id="014cf-120">For more information, see [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span></span>  
  
### <a name="to-use-an-installshield-limited-edition-project"></a><span data-ttu-id="014cf-121">Использование проекта InstallShield Limited Edition</span><span class="sxs-lookup"><span data-stu-id="014cf-121">To use an InstallShield Limited Edition Project</span></span>  
  
1.  <span data-ttu-id="014cf-122">Добавьте пакет настройки и развертывания в свое решение, открыв контекстное меню решения и выбрав **Добавить**, **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="014cf-122">Add a setup and deployment package to your solution by opening the shortcut menu for your solution, and then choosing **Add**, **New Project**.</span></span>  
  
2.  <span data-ttu-id="014cf-123">В диалоговом окне **Добавление нового проекта** в папке **Установленные** выберите **Другие типы проектов**, **Установка и развертывание**, **InstallShield Limited Edition** и присвойте проекту имя.</span><span class="sxs-lookup"><span data-stu-id="014cf-123">In the **Add New Project** dialog box, in the **Installed** folder, choose **Other Project Types**,  **Setup and Deployment**, **InstallShield Limited Edition**, and give your project a name.</span></span> <span data-ttu-id="014cf-124">(При отображении запроса загрузите, установите и активируйте InstallShield.)</span><span class="sxs-lookup"><span data-stu-id="014cf-124">(If prompted, download, install, and activate InstallShield.)</span></span>  
  
3.  <span data-ttu-id="014cf-125">Выполните общую настройку проекта установки и развертывания с использованием помощника по проектам в **обозревателе решений** или с помощью подэтапов нумерованных этапов в **Обозревателе решений**. Настройте установку так же, как и без добавления сборок в GAC.</span><span class="sxs-lookup"><span data-stu-id="014cf-125">Perform the general configuration of your setup and deployment project either by using the Project Assistant in **Solution Explorer**, or by choosing the substeps of the numbered steps in the **Solution Explorer**.Configure your setup as you would if you were not adding assemblies to the GAC.</span></span>  
  
4.  <span data-ttu-id="014cf-126">Чтобы начать процесс добавления сборки в глобальный кэш сборок, выберите **Файлы** на этапе **Определение данных приложения** в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="014cf-126">To begin the process of adding an assembly to the GAC, choose **Files**, which is under the **Specify Application Data** step in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="014cf-127">В области **Папки целевого компьютера** откройте контекстное меню **Целевой компьютер**, после чего выберите **Показывать предварительно определенную папку**, **[GlobalAssemblyCache]**.</span><span class="sxs-lookup"><span data-stu-id="014cf-127">In the **Destination computer's folders** pane, open the shortcut menu for **Destination Computer**, and then choose **Show Predefined Folder**, **[GlobalAssemblyCache]**.</span></span>  
  
6.  <span data-ttu-id="014cf-128">Для каждого проекта в решении, содержащем сборку, которую нужно установить в глобальном кэше сборок:</span><span class="sxs-lookup"><span data-stu-id="014cf-128">For each project in the solution that contains an assembly that you want to install in the global assembly cache:</span></span>  
  
    1.  <span data-ttu-id="014cf-129">В области **Папки исходного компьютера** выберите проект.</span><span class="sxs-lookup"><span data-stu-id="014cf-129">In the **Source computer's folders** pane, choose the project.</span></span>  
  
    2.  <span data-ttu-id="014cf-130">В области **Папки целевого компьютера** выберите **[GlobalAssemblyCache]**.</span><span class="sxs-lookup"><span data-stu-id="014cf-130">In the **Destination computer's folders** pane, choose **[GlobalAssemblyCache]**.</span></span>  
  
    3.  <span data-ttu-id="014cf-131">В области **Файлы исходного компьютера** выберите **Основные выходные файлы** *<имя_проекта>*.</span><span class="sxs-lookup"><span data-stu-id="014cf-131">In the **Source computer's files** pane, choose **Primary output from** *<project_name>*.</span></span>  
  
    4.  <span data-ttu-id="014cf-132">На шаге C перетащите файл в область **Файлы целевого компьютера** (или воспользуйтесь командами **Копировать** и **Вставить** в контекстном меню).</span><span class="sxs-lookup"><span data-stu-id="014cf-132">Drag the file in step c to the **Destination computer's files** pane (or use the **Copy** and **Paste** commands from the file's shortcut menu).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="014cf-133">См. также</span><span class="sxs-lookup"><span data-stu-id="014cf-133">See Also</span></span>  
 [<span data-ttu-id="014cf-134">Работа со сборками и глобальным кэшем сборок</span><span class="sxs-lookup"><span data-stu-id="014cf-134">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="014cf-135">Практическое руководство. Удаление сборки из глобального кэша сборок</span><span class="sxs-lookup"><span data-stu-id="014cf-135">How to: Remove an Assembly from the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 [<span data-ttu-id="014cf-136">Gacutil.exe (программа глобального кэша сборок)</span><span class="sxs-lookup"><span data-stu-id="014cf-136">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)  
 [<span data-ttu-id="014cf-137">Практическое руководство. Подписание сборки строгим именем</span><span class="sxs-lookup"><span data-stu-id="014cf-137">How to: Sign an Assembly with a Strong Name</span></span>](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [<span data-ttu-id="014cf-138">Развертывание с помощью установщика Windows</span><span class="sxs-lookup"><span data-stu-id="014cf-138">Windows Installer Deployment</span></span>](http://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0)
