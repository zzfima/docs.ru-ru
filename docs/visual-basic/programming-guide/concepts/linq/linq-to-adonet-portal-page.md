---
title: LINQ to ADO.NET (Страница портала)
ms.date: 07/20/2015
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
ms.openlocfilehash: 21d6ddb4b793d2502b315888d79fb826741fed2e
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307483"
---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (Страница портала)
[!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] позволяет запрашивать любой перечисляемый объект в ADO.NET с помощью модели программирования [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].  
  
> [!NOTE]
>  Документация по [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] находится в разделе ADO.NET пакета SDK для .NET Framework: [LINQ и ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md).
  
 Существуют три отдельные технологии ADO.NET [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] и [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] обеспечивает расширенные и оптимизированные запросы к <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] позволяет непосредственно запрашивать схемы баз данных SQL Server, и [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] позволяет выполнять запросы к модели EDM.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> является одним из наиболее широко используемых компонентов в ADO.NET и ключевым элементом модели автономного программирования, на основе которой создан ADO.NET. Несмотря на все это, объект <xref:System.Data.DataSet> имеет ограниченные возможности запросов.  
  
 [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] позволяет использовать расширенные возможности запросов в <xref:System.Data.DataSet> с применением той же функциональности, которая доступна для многих других источников данных.  
  
 Дополнительные сведения см. в разделе [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] предоставляет инфраструктуру времени выполнения для управления реляционными данными в виде объектов. В [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] модель данных реляционной базы данных сопоставляется объектной модели, выраженной в языке программирования разработчика. При выполнении приложения [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] преобразует интегрированные в язык запросы из объектной модели в SQL и отправляет их в базу данных для выполнения. Когда база данных возвращает результаты, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] переводит их обратно в объекты, которыми можно управлять.  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] включает поддержку хранимых процедур, определяемых пользователем функций в базе данных и наследования в объектной модели.  
  
 Дополнительные сведения см. в разделе [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 Через модель EDM реляционные данные представлены в виде объектов в среде .NET. Благодаря этому поддержка [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] эффективно реализуется на уровне объектов, что позволяет составлять запросы баз данных на языке, используемом для сборки бизнес-логики. Эта функция называется [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. Дополнительные сведения см. в разделе [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>См. также

- [LINQ и ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)
- [Синтаксис LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
