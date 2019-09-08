---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 4995512336ee9eb6e33df011757ed533db57e76e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783784"
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
LINQ to DataSet упрощает и ускоряет выполнение запросов к данным, <xref:System.Data.DataSet> кэшированным в объекте. В частности, LINQ to DataSet упрощает выполнение запросов, позволяя разработчикам писать запросы с самого языка программирования, а не с помощью отдельного языка запросов. Это особенно удобно для разработчиков Visual Studio, которые теперь могут использовать преимущества проверки синтаксиса во время компиляции, статическую типизацию и поддержку IntelliSense, предоставляемую Visual Studio в своих запросах.  
  
 LINQ to DataSet также можно использовать для запроса данных, консолидированных из одного или нескольких источников данных. Это удовлетворяет многим сценариям, требующим гибкости при представлении и обработке данных, таких как запросы к данным, прошедшим локальную агрегатную обработку, и кэширование на среднем уровне в веб-приложениях. В частности, этот метод обработки требуется для универсальных приложений отчетности, анализа и бизнес-аналитики.  
  
 Функции LINQ to DataSet предоставляются главным образом через методы расширения в <xref:System.Data.DataRowExtensions> классах и. <xref:System.Data.DataTableExtensions> LINQ to DataSet строится на основе существующей архитектуры ADO.NET и не предназначена для замены ADO.NET в коде приложения. Существующий код ADO.NET будет продолжать работать в приложении LINQ to DataSet. Отношение LINQ to DataSet к ADO.NET и хранилищу данных показано на следующей схеме.  
  
 ![Схема, показывающая, что LINQ to DataSet основан на поставщике ADO.NET.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a>В этом разделе  
 [Начало работы](getting-started-linq-to-dataset.md)  
  
 [Руководство по программированию](programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>См. также

- [LINQ — C#](../../../csharp/programming-guide/concepts/linq/index.md)
- [LINQ — Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ и ADO.NET](linq-and-ado-net.md)
- [ADO.NET](index.md)
