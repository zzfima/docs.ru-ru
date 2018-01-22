---
title: "Практическое руководство. Создание проектов LINQ to DataSet в Visual Studio"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c749cdd56f0c964b84788b05470406234ef3eb0a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="38bd7-102">Практическое руководство. Создание проектов LINQ to DataSet в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="38bd7-102">How to: Create a LINQ to DataSet Project In Visual Studio</span></span>
<span data-ttu-id="38bd7-103">Различные типы проектов [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] требуют импорта определенных пространств имен (Visual Basic) или директив `using` (C#) и ссылок.</span><span class="sxs-lookup"><span data-stu-id="38bd7-103">The different types of [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] projects require certain imported namespaces (Visual Basic) or `using` directives (C#) and references.</span></span> <span data-ttu-id="38bd7-104">Минимальными требованиями являются наличие ссылки на библиотеку System.Core.dll и директивы `using` пространства имен <xref:System.Linq>.</span><span class="sxs-lookup"><span data-stu-id="38bd7-104">The minimum requirement is a reference to System.Core.dll and a `using` directive for <xref:System.Linq>.</span></span> <span data-ttu-id="38bd7-105">По умолчанию они добавляются при создании нового проекта [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38bd7-105">By default, these are supplied if you create a new [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)] project.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="38bd7-106"> также требует наличия ссылок на System.Data.dll и System.Data.DataSetExtensions.dll и директивы `Imports` (Visual Basic) или `using` (C#).</span><span class="sxs-lookup"><span data-stu-id="38bd7-106"> also requires a reference to System.Data.dll and System.Data.DataSetExtensions.dll and an `Imports` (Visual Basic) or `using` (C#) directive.</span></span>  
  
 <span data-ttu-id="38bd7-107">Если обновляется проект более ранней версии Visual Studio, связанные с LINQ ссылки, возможно, придется добавить вручную.</span><span class="sxs-lookup"><span data-stu-id="38bd7-107">If you are upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span> <span data-ttu-id="38bd7-108">Также может понадобиться вручную указать для проекта требуемую версию .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="38bd7-108">You might also have to manually set the project to target the .NET Framework version 3.5.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38bd7-109">При построении из командной строки необходимо вручную сослаться на связанные с LINQ библиотеки DLL в `drive` **:**\Program Files\Reference Assemblies\Microsoft\Framework\v3.5.</span><span class="sxs-lookup"><span data-stu-id="38bd7-109">If you are building from a command prompt, you must manually reference the LINQ-related DLLs in `drive`**:**\Program Files\Reference Assemblies\Microsoft\Framework\v3.5.</span></span>  
  
### <a name="to-target-the-net-framework-35"></a><span data-ttu-id="38bd7-110">Платформа Microsoft .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="38bd7-110">To target the .NET Framework 3.5</span></span>  
  
1.  <span data-ttu-id="38bd7-111">В среде [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] создайте новый проект Visual Basic или C#.</span><span class="sxs-lookup"><span data-stu-id="38bd7-111">In [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)], create a new Visual Basic or C# project.</span></span> <span data-ttu-id="38bd7-112">Или откройте проект Visual Basic или C#, созданный в среде Visual Studio 2005, и следуйте подсказкам для преобразования его в проект [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38bd7-112">Alternatively, you can open a Visual Basic or C# project that was created in Visual Studio 2005 and follow the prompts to convert it to a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="38bd7-113">В проекте C# выберите **проекта** меню, а затем нажмите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="38bd7-113">For a C# project, click the **Project** menu, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="38bd7-114">В **приложения** страницу свойств, выберите платформу .NET Framework 3.5 в **требуемой версии .NET Framework** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="38bd7-114">In the **Application** property page, select .NET Framework 3.5 in the **Target Framework** drop-down list.</span></span>  
  
3.  <span data-ttu-id="38bd7-115">В проекте Visual Basic выберите **проекта** меню, а затем нажмите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="38bd7-115">For a Visual Basic project, click the **Project** menu, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="38bd7-116">В **компиляции** страницу свойств, нажмите кнопку **Дополнительные параметры компиляции** и установите платформу .NET Framework 3.5 в **требуемая версия .NET Framework (все конфигурации)** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="38bd7-116">In the **Compile** property page, click **Advanced Compile Options** and then select .NET Framework 3.5 in the **Target Framework (all configurations)** drop-down list.</span></span>  
  
4.  <span data-ttu-id="38bd7-117">На **проекта** меню, нажмите кнопку **добавить ссылку**, нажмите кнопку **.NET** Перейдите вниз к **System.Core**, щелкните его и нажмите кнопку  **ОК**.</span><span class="sxs-lookup"><span data-stu-id="38bd7-117">On the **Project** menu, click **Add Reference**, click the **.NET** tab, scroll down to **System.Core**, click it, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="38bd7-118">Добавьте директиву `using` или импортированное пространство имен для <xref:System.Linq> в файл исходного кода или проект.</span><span class="sxs-lookup"><span data-stu-id="38bd7-118">Add a `using` directive or imported namespace for <xref:System.Linq> to your source code file or project.</span></span>  
  
     <span data-ttu-id="38bd7-119">Дополнительные сведения см. в разделе [с помощью директивы](~/docs/csharp/language-reference/keywords/using-directive.md) или [как: Добавление или удаление Импортируемые пространства имен (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="38bd7-119">For more information, see [using Directive](~/docs/csharp/language-reference/keywords/using-directive.md) or [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
### <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="38bd7-120">Включение функциональности LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="38bd7-120">To enable LINQ to DataSet functionality</span></span>  
  
1.  <span data-ttu-id="38bd7-121">При необходимости выполните шаги, описанные выше в этом разделе, чтобы добавить ссылку на библиотеку System.Core.dll и директиву `using` или импортированное пространство имен System.Linq.</span><span class="sxs-lookup"><span data-stu-id="38bd7-121">If necessary, follow the steps earlier in this topic to add a reference to System.Core.dll and a `using` directive or imported namespace for System.Linq.</span></span>  
  
2.  <span data-ttu-id="38bd7-122">В C# или Visual Basic выберите **проекта** меню, а затем нажмите **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="38bd7-122">In C# or Visual Basic, click the **Project** menu, and then click **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="38bd7-123">В **добавить ссылку** диалоговое окно, нажмите кнопку **.NET** вкладки, если это не в верхней части.</span><span class="sxs-lookup"><span data-stu-id="38bd7-123">In the **Add Reference** dialog box, click the **.NET** tab if it is not on top.</span></span> <span data-ttu-id="38bd7-124">Прокрутите вниз до **System.Data** и **System.Data.DataSetExtensions** и щелкните их.</span><span class="sxs-lookup"><span data-stu-id="38bd7-124">Scroll down to **System.Data** and **System.Data.DataSetExtensions** and click on them.</span></span> <span data-ttu-id="38bd7-125">Нажмите кнопку **ОК** кнопки.</span><span class="sxs-lookup"><span data-stu-id="38bd7-125">Click the **OK** button.</span></span>  
  
4.  <span data-ttu-id="38bd7-126">Добавьте директиву `using` или импортированное пространство имен для <xref:System.Data> в файл исходного кода или проект.</span><span class="sxs-lookup"><span data-stu-id="38bd7-126">Add a `using` directive or imported namespace for <xref:System.Data> to your source code file or project.</span></span> <span data-ttu-id="38bd7-127">Дополнительные сведения см. в разделе [с помощью директивы](~/docs/csharp/language-reference/keywords/using-directive.md) или [как: Добавление или удаление Импортируемые пространства имен (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="38bd7-127">For more information, see [using Directive](~/docs/csharp/language-reference/keywords/using-directive.md) or [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
5.  <span data-ttu-id="38bd7-128">Добавьте ссылку на библиотеку System.Data.DataSetExtensions.dll для поддержки LINQ to Dataset.</span><span class="sxs-lookup"><span data-stu-id="38bd7-128">Add a reference to System.Data.DataSetExtensions.dll for LINQ to Dataset functionality.</span></span> <span data-ttu-id="38bd7-129">Создайте ссылку на библиотеку System.Data.dll, если она не существует.</span><span class="sxs-lookup"><span data-stu-id="38bd7-129">Add a reference to System.Data.dll if it does not already exist.</span></span>  
  
6.  <span data-ttu-id="38bd7-130">Дополнительно можно добавить директиву `using` или импортированное пространство имен для `System.Data.Common` или `System.Data.SqlClient` в зависимости от способа подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="38bd7-130">Optionally, add a `using` directive or imported namespace for `System.Data.Common` or `System.Data.SqlClient`, depending on how you connect to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38bd7-131">См. также</span><span class="sxs-lookup"><span data-stu-id="38bd7-131">See Also</span></span>  
 [<span data-ttu-id="38bd7-132">Начало работы</span><span class="sxs-lookup"><span data-stu-id="38bd7-132">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
 [<span data-ttu-id="38bd7-133">Начало работы с LINQ</span><span class="sxs-lookup"><span data-stu-id="38bd7-133">Getting Started with LINQ</span></span>](http://msdn.microsoft.com/library/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)
