---
title: LINQ to ADO.NET (Страница портала)
ms.date: 07/20/2015
ms.assetid: 6bd269b4-3509-4688-b672-836008704182
ms.openlocfilehash: 84412e43a9d6b1e256e4ac8306a94126a3eaaaf4
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635552"
---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (Страница портала)
LINQ to ADO.NET позволяет запрашивать любой перечисляемый объект в ADO.NET с помощью модели программирования LINQ.  
  
> [!NOTE]
> Документация по LINQ to ADO.NET находится в разделе ADO.NET пакета SDK для .NET Framework: [LINQ и ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md).  
  
 Существуют три отдельные технологии ADO.NET LINQ: LINQ to DataSet, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] и LINQ to Entities. Технология LINQ to DataSet обеспечивает расширенные и оптимизированные запросы к <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] позволяет запрашивать непосредственно схемы базы данных SQL Server, а LINQ to Entities — выполнять запросы к EDM.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> является одним из наиболее широко используемых компонентов в ADO.NET и ключевым элементом модели автономного программирования, на основе которой создан ADO.NET. Несмотря на все это, объект <xref:System.Data.DataSet> имеет ограниченные возможности запросов.  
  
 LINQ to DataSet позволяет использовать расширенные возможности запросов в <xref:System.Data.DataSet> — те же функции, что и для многих других источников данных.  
  
 Дополнительные сведения см. в разделе [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] предоставляет инфраструктуру времени выполнения для управления реляционными данными в виде объектов. В [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] модель данных реляционной базы данных сопоставляется объектной модели, выраженной в языке программирования разработчика. При выполнении приложения [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] преобразует интегрированные в язык запросы из объектной модели в SQL и отправляет их в базу данных для выполнения. Когда база данных возвращает результаты, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] переводит их обратно в объекты, которыми можно управлять.  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] включает поддержку хранимых процедур, определяемых пользователем функций в базе данных и наследования в объектной модели.  
  
 Дополнительные сведения см. в разделе [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 В модели EDM реляционные данные представлены в виде объектов в среде .NET. Благодаря этому поддержка LINQ эффективно реализуется на уровне объектов, что позволяет составлять запросы баз данных на языке, используемом для сборки бизнес-логики. Эта функция называется LINQ to Entities. Дополнительные сведения см. в разделе [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>См. также

- [LINQ и ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)
- [LINQ (C#)](./index.md)
