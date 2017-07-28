---
title: "Как создать проект LINQ to DataSet в среде Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как создать проект LINQ to DataSet в среде Visual Studio
Различные типы проектов [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] требуют импорта определенных пространств имен \(Visual Basic\) или директив `using` \(C\#\) и ссылок.  Минимальными требованиями являются наличие ссылки на библиотеку System.Core.dll и директивы `using` пространства имен <xref:System.Linq>.  По умолчанию они добавляются при создании нового проекта [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)].  [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] также требует наличия ссылок на System.Data.dll и System.Data.DataSetExtensions.dll и директивы `Imports` \(Visual Basic\) или `using` \(C\#\).  
  
 Если обновляется проект более ранней версии Visual Studio, связанные с LINQ ссылки, возможно, придется добавить вручную.  Также может понадобиться вручную указать для проекта требуемую версию .NET Framework 3.5.  
  
> [!NOTE]
>  При работе из командной строки необходимо вручную указать ссылки на связанные с LINQ библиотеки DLL в папке `drive`**:**\\Program Files\\Reference Assemblies\\Microsoft\\Framework\\v3.5.  
  
### Платформа Microsoft .NET Framework 3.5  
  
1.  Создайте новый проект Visual Basic или C\# в среде [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] либо откройте проект Visual Basic или C\#, созданный в среде Visual Studio 2005, и следуйте подсказкам для его преобразования в проект [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  В случае проекта C\# в меню **Проект** выберите команду **Свойства**.  
  
    1.  На странице свойств **Приложение** в раскрывающемся списке **Требуемая версия .NET Framework** выберите «.NET Framework 3.5».  
  
3.  Для проекта Visual Basic в меню **Проект** выберите пункт **Свойства**.  
  
    1.  На странице свойств **Компиляция** нажмите кнопку **Дополнительные параметры компиляции** и в раскрывающемся списке **Требуемая версия .NET Framework \(все конфигурации\)** выберите «.NET Framework 3.5».  
  
4.  В меню **Проект** выберите команду **Добавить ссылку**, перейдите на вкладку **.NET**, прокрутите список до пункта **System.Core**, щелкните его и нажмите кнопку **ОК**.  
  
5.  Добавьте директиву `using` или импортированное пространство имен для <xref:System.Linq> в файл исходного кода или проект.  
  
     Дополнительные сведения см. в разделе [Директива using](../Topic/using%20Directive%20\(C%23%20Reference\).md) или [Практическое руководство. Добавление или удаление импортированных пространств имен \(Visual Basic\)](../Topic/How%20to:%20Add%20or%20Remove%20Imported%20Namespaces%20\(Visual%20Basic\).md).  
  
### Включение функциональности LINQ to DataSet  
  
1.  При необходимости выполните шаги, описанные выше в этом разделе, чтобы добавить ссылку на библиотеку System.Core.dll и директиву `using` или импортированное пространство имен System.Linq.  
  
2.  В проекте C\# или Visual Basic в меню **Проект** выберите команду **Добавить ссылку**.  
  
3.  В диалоговом окне **Добавление ссылки** перейдите на вкладку **.NET**, если она неактивна.  Прокрутите список до пунктов **System.Data** и **System.Data.DataSetExtensions** и щелкните их.  Нажмите кнопку **ОК**.  
  
4.  Добавьте директиву `using` или импортированное пространство имен для <xref:System.Data> в файл исходного кода или проект.  Дополнительные сведения см. в разделе [Директива using](../Topic/using%20Directive%20\(C%23%20Reference\).md) или [Практическое руководство. Добавление или удаление импортированных пространств имен \(Visual Basic\)](../Topic/How%20to:%20Add%20or%20Remove%20Imported%20Namespaces%20\(Visual%20Basic\).md).  
  
5.  Добавьте ссылку на библиотеку System.Data.DataSetExtensions.dll для поддержки LINQ to Dataset.  Создайте ссылку на библиотеку System.Data.dll, если она не существует.  
  
6.  Дополнительно можно добавить директиву `using` или импортированное пространство имен для `System.Data.Common` или `System.Data.SqlClient` в зависимости от способа подключения к базе данных.  
  
## См. также  
 [Приступая к работе](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)   
 [Getting Started with LINQ](http://msdn.microsoft.com/ru-ru/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)