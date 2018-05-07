---
title: Запросы к наборам данных (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: 18daed2ee4196a03af818dfbd0e65153ae43a840
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="querying-datasets-linq-to-dataset"></a>Запросы к наборам данных (LINQ to DataSet)
После того как в объекте <xref:System.Data.DataSet> появятся данные, к нему можно выполнять запросы. Составление запросов с использованием [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] похоже на использование [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] с другими источниками данных, поддерживающих [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]. Однако следует помнить, что при использовании [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] запросов по <xref:System.Data.DataSet> запрашивается перечисление <xref:System.Data.DataRow> объектов вместо перечисления пользовательского типа. Это означает, что можно использовать любой из членов <xref:System.Data.DataRow> класса в вашей [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] запросов. Это позволяет создавать мощные, сложные запросы.  
  
 Как и в случае с другими реализациями [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], можно создать [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] запросов в двух различных видов: синтаксис выражений запросов и синтаксис запросов на основе методов. Дополнительные сведения об этих двух форм см. в разделе [Приступая к работе с LINQ](http://msdn.microsoft.com/library/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9). Синтаксис выражений запросов или синтаксис запросов на основе методов можно использовать для выполнения запросов к отдельным таблицам в <xref:System.Data.DataSet>, к нескольким таблицам в <xref:System.Data.DataSet> или к таблицам в типизированном <xref:System.Data.DataSet>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Запросы к одной таблице](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 Описывается выполнение запросов к отдельным таблицам.  
  
 [Запросы между таблицами](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 Описывается выполнение межтабличных запросов.  
  
 [Запрос к типизированным объектам DataSet](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 Описываются запросы к типизированным объектам <xref:System.Data.DataSet>.  
  
## <a name="see-also"></a>См. также  
 [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [Загрузка данных в DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
