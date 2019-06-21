---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 36335f90c7850fa00a15e7112b7473637250c656
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306234"
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] упрощает и ускоряет запросы к данным, кэшированным в объекте <xref:System.Data.DataSet>. В частности [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] упрощает создание запросов, позволяя разработчикам писать запросы в языке программирования, а не используя отдельный язык запросов. Это особенно полезно для разработчиков Visual Studio, которые теперь могут воспользоваться преимуществами проверку синтаксиса во время компиляции, статическую типизацию и поддержку технологии IntelliSense, предоставляемые Visual Studio в своих запросах.  
  
 Технология [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] также может использоваться для запросов к данным, находящимся в одном или нескольких источниках. Это удовлетворяет многим сценариям, требующим гибкости при представлении и обработке данных, таких как запросы к данным, прошедшим локальную агрегатную обработку, и кэширование на среднем уровне в веб-приложениях. В частности, этот метод обработки требуется для универсальных приложений отчетности, анализа и бизнес-аналитики.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Предоставляется в основном через методы расширения в <xref:System.Data.DataRowExtensions> и <xref:System.Data.DataTableExtensions> классы. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] основан на использует существующую архитектуру ADO.NET и не предназначен для замены ADO.NET в коде приложения. Существующий код ADO.NET продолжит работать в [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] приложения. Связь между [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] хранилищем для ADO.NET, а также данных показана на следующей схеме.  
  
 ![Схема, показывающая, что LINQ to DataSet основана на поставщике ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a>В этом разделе  
 [Начало работы](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [Руководство по программированию](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>См. также

- [LINQ — C#](../../../csharp/programming-guide/concepts/linq/index.md)
- [LINQ — Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ и ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
