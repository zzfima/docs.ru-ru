---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 9769e98d1046bbe795040782ca5d8164140b4b0d
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904855"
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] упрощает и ускоряет запросы к данным, кэшированным в объекте <xref:System.Data.DataSet>. В частности [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] упрощает создание запросов, позволяя разработчикам писать запросы в языке программирования, а не используя отдельный язык запросов. Это особенно полезно для разработчиков Visual Studio, которые теперь могут воспользоваться преимуществами проверку синтаксиса во время компиляции, статическую типизацию и поддержку технологии IntelliSense, предоставляемые Visual Studio в своих запросах.  
  
 Технология [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] также может использоваться для запросов к данным, находящимся в одном или нескольких источниках. Это удовлетворяет многим сценариям, требующим гибкости при представлении и обработке данных, таких как запросы к данным, прошедшим локальную агрегатную обработку, и кэширование на среднем уровне в веб-приложениях. В частности, этот метод обработки требуется для универсальных приложений отчетности, анализа и бизнес-аналитики.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Предоставляется в основном через методы расширения в <xref:System.Data.DataRowExtensions> и <xref:System.Data.DataTableExtensions> классы. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] основывается на и использует существующую [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] архитектуры и не предназначен для замены [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] в коде приложения. Существующий код ADO.NET 2.0 продолжит работать в приложении [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Связь между [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] и [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] и хранилищем данных показана на следующей схеме.  
  
 ![Технология LINQ to DataSet основана на поставщике ADO.NET](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")  
  
## <a name="in-this-section"></a>В этом разделе  
 [Начало работы](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [Руководство по программированию](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>См. также
- [Language-Integrated Query (LINQ):C#](../../../csharp/programming-guide/concepts/linq/index.md)
- [Language-Integrated Query (LINQ): Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ и ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
