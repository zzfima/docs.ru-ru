---
title: "LINQ to DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# LINQ to DataSet
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] упрощает и ускоряет запросы к данным, кэшированным в объекте <xref:System.Data.DataSet>.  В особенности [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] упрощает создание запросов, позволяя писать их непосредственно на языке программирования, а не применять отдельный язык запросов.  Это особенно полезно для разработчиков среды [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], которые теперь могут воспользоваться в своих запросах преимуществами проверки синтаксиса во время компиляции, статической типизации и поддержки технологии IntelliSense, обеспечиваемой средой [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
 Технология [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] также может использоваться для запросов к данным, находящимся в одном или нескольких источниках.  Это удовлетворяет многим сценариям, требующим гибкости при представлении и обработке данных, таких как запросы к данным, прошедшим локальную агрегатную обработку, и кэширование на среднем уровне в веб\-приложениях.  В частности, этот метод обработки требуется для универсальных приложений отчетности, анализа и бизнес\-аналитики.  
  
 Технология [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] в первую очередь используются в методах расширений в классах <xref:System.Data.DataRowExtensions> и <xref:System.Data.DataTableExtensions>. Технология [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] построена на основе архитектуры [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] и использует ее, но не заменяет [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] в коде приложения.  Существующий код ADO.NET 2.0 продолжит работать в приложении [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Связь между [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] и [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] и хранилищем данных показана на следующей схеме.  
  
 ![Технология LINQ to DataSet базируется на поставщике ADO.NET.](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")  
  
## В этом подразделе  
 [Приступая к работе](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [Руководство по программированию](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## Ссылка  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## См. также  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [LINQ и ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)   
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)