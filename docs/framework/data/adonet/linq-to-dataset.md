---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: c4069ef760877935c4ce194144d131d0dc58b4d3
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504363"
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
LINQ to DataSet позволяет проще и быстрее для запросов к данным кэшируются в <xref:System.Data.DataSet> объекта. В частности LINQ to DataSet упрощает создание запросов, позволяя разработчикам писать запросы в языке программирования, а не используя отдельный язык запросов. Это особенно полезно для разработчиков Visual Studio, которые теперь могут воспользоваться преимуществами проверку синтаксиса во время компиляции, статическую типизацию и поддержку технологии IntelliSense, предоставляемые Visual Studio в своих запросах.  
  
 Также можно использовать LINQ to DataSet для запросов к данным, находящимся в одной или нескольких источников данных. Это удовлетворяет многим сценариям, требующим гибкости при представлении и обработке данных, таких как запросы к данным, прошедшим локальную агрегатную обработку, и кэширование на среднем уровне в веб-приложениях. В частности, этот метод обработки требуется для универсальных приложений отчетности, анализа и бизнес-аналитики.  
  
 LINQ to DataSet функциональность предоставляется в основном через методы расширения в <xref:System.Data.DataRowExtensions> и <xref:System.Data.DataTableExtensions> классы. LINQ to DataSet основана на и использует существующую архитектуру ADO.NET и не предназначен для замены ADO.NET в коде приложения. Существующий код ADO.NET будет продолжать работать в LINQ to DataSet приложения. На следующей схеме показана связь между LINQ to DataSet ADO.NET и хранилище данных.  
  
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
