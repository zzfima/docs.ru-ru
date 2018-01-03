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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6710d3e9bf52ff10ee8dd545161f0858001f2c40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>Практическое руководство. Создание проектов LINQ to DataSet в Visual Studio
Различные типы проектов [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] требуют импорта определенных пространств имен (Visual Basic) или директив `using` (C#) и ссылок. Минимальными требованиями являются наличие ссылки на библиотеку System.Core.dll и директивы `using` пространства имен <xref:System.Linq>. По умолчанию они добавляются при создании нового проекта [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)]. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] также требует наличия ссылок на System.Data.dll и System.Data.DataSetExtensions.dll и директивы `Imports` (Visual Basic) или `using` (C#).  
  
 Если обновляется проект более ранней версии Visual Studio, связанные с LINQ ссылки, возможно, придется добавить вручную. Также может понадобиться вручную указать для проекта требуемую версию .NET Framework 3.5.  
  
> [!NOTE]
>  При построении из командной строки необходимо вручную сослаться на связанные с LINQ библиотеки DLL в `drive` **:**\Program Files\Reference Assemblies\Microsoft\Framework\v3.5.  
  
### <a name="to-target-the-net-framework-35"></a>Платформа Microsoft .NET Framework 3.5  
  
1.  В среде [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] создайте новый проект Visual Basic или C#. Или откройте проект Visual Basic или C#, созданный в среде Visual Studio 2005, и следуйте подсказкам для преобразования его в проект [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  В проекте C# выберите **проекта** меню, а затем нажмите **свойства**.  
  
    1.  В **приложения** страницу свойств, выберите платформу .NET Framework 3.5 в **требуемой версии .NET Framework** раскрывающегося списка.  
  
3.  В проекте Visual Basic выберите **проекта** меню, а затем нажмите **свойства**.  
  
    1.  В **компиляции** страницу свойств, нажмите кнопку **Дополнительные параметры компиляции** и установите платформу .NET Framework 3.5 в **требуемая версия .NET Framework (все конфигурации)** раскрывающегося списка.  
  
4.  На **проекта** меню, нажмите кнопку **добавить ссылку**, нажмите кнопку **.NET** Перейдите вниз к **System.Core**, щелкните его и нажмите кнопку  **ОК**.  
  
5.  Добавьте директиву `using` или импортированное пространство имен для <xref:System.Linq> в файл исходного кода или проект.  
  
     Дополнительные сведения см. в разделе [с помощью директивы](~/docs/csharp/language-reference/keywords/using-directive.md) или [как: Добавление или удаление Импортируемые пространства имен (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).  
  
### <a name="to-enable-linq-to-dataset-functionality"></a>Включение функциональности LINQ to DataSet  
  
1.  При необходимости выполните шаги, описанные выше в этом разделе, чтобы добавить ссылку на библиотеку System.Core.dll и директиву `using` или импортированное пространство имен System.Linq.  
  
2.  В C# или Visual Basic выберите **проекта** меню, а затем нажмите **добавить ссылку**.  
  
3.  В **добавить ссылку** диалоговое окно, нажмите кнопку **.NET** вкладки, если это не в верхней части. Прокрутите вниз до **System.Data** и **System.Data.DataSetExtensions** и щелкните их. Нажмите кнопку **ОК** кнопки.  
  
4.  Добавьте директиву `using` или импортированное пространство имен для <xref:System.Data> в файл исходного кода или проект. Дополнительные сведения см. в разделе [с помощью директивы](~/docs/csharp/language-reference/keywords/using-directive.md) или [как: Добавление или удаление Импортируемые пространства имен (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).  
  
5.  Добавьте ссылку на библиотеку System.Data.DataSetExtensions.dll для поддержки LINQ to Dataset. Создайте ссылку на библиотеку System.Data.dll, если она не существует.  
  
6.  Дополнительно можно добавить директиву `using` или импортированное пространство имен для `System.Data.Common` или `System.Data.SqlClient` в зависимости от способа подключения к базе данных.  
  
## <a name="see-also"></a>См. также  
 [Начало работы](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
 [Начало работы с LINQ](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)
