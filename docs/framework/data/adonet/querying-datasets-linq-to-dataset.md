---
title: Запросы к наборам данных (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: 79a9b320fbdbfecc3f7d531d992b1529873871a5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783046"
---
# <a name="querying-datasets-linq-to-dataset"></a>Запросы к наборам данных (LINQ to DataSet)
После того как в объекте <xref:System.Data.DataSet> появятся данные, к нему можно выполнять запросы. Запросы составления с LINQ to DataSet похожи на использование [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] с источниками данных с поддержкой других [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]источников. Однако помните, что при использовании [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] запросов <xref:System.Data.DataSet> через объект вы <xref:System.Data.DataRow> запрашиваете перечисление объектов, а не перечисление настраиваемого типа. Это означает, что <xref:System.Data.DataRow> [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] в запросах можно использовать любой из членов класса. Это позволяет создавать мощные, сложные запросы.  
  
 Как и в других реализациях [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], запросы LINQ to DataSet можно создавать в двух разных формах: синтаксис выражений запроса и синтаксис запросов на основе методов. Синтаксис выражений запросов или синтаксис запросов на основе методов можно использовать для выполнения запросов к отдельным таблицам в <xref:System.Data.DataSet>, к нескольким таблицам в <xref:System.Data.DataSet> или к таблицам в типизированном <xref:System.Data.DataSet>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Запросы к одной таблице](single-table-queries-linq-to-dataset.md)  
 Описывается выполнение запросов к отдельным таблицам.  
  
 [Запросы между таблицами](cross-table-queries-linq-to-dataset.md)  
 Описывается выполнение межтабличных запросов.  
  
 [Запрос к типизированным объектам DataSet](querying-typed-datasets.md)  
 Описываются запросы к типизированным объектам <xref:System.Data.DataSet>.  
  
## <a name="see-also"></a>См. также

- [Примеры LINQ to DataSet](linq-to-dataset-examples.md)
- [Загрузка данных в DataSet](loading-data-into-a-dataset.md)
