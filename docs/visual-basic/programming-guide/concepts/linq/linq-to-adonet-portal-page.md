---
title: LINQ to ADO.NET (Страница портала)
ms.date: 07/20/2015
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
ms.openlocfilehash: 424a4639677d6066fa5cac74e370ca76ebcaea60
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43803865"
---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (Страница портала)
[!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] позволяет запрашивать любой перечисляемый объект [!INCLUDE[vstecado](~/includes/vstecado-md.md)] с помощью модели программирования [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].  
  
> [!NOTE]
>  Документация по [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] находится в разделе ADO.NET пакета SDK для .NET Framework: [LINQ и ADO.NET](https://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).  
  
 Существуют три отдельные технологии ADO.NET [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] и [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. Технология [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] обеспечивает расширенные и оптимизированные запросы к <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] позволяет запрашивать непосредственно схемы базы данных SQL Server, а [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] — выполнять запросы к [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)].  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> является одним из наиболее широко используемых компонентов в [!INCLUDE[vstecado](~/includes/vstecado-md.md)] и представляет собой ключевой элемент в модели отсоединенного программирования, на которой построен [!INCLUDE[vstecado](~/includes/vstecado-md.md)]. Несмотря на все это, объект <xref:System.Data.DataSet> имеет ограниченные возможности запросов.  
  
 [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] позволяет использовать расширенные возможности запросов в <xref:System.Data.DataSet> с применением той же функциональности, которая доступна для многих других источников данных.  
  
 Дополнительные сведения см. в разделе [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] предоставляет инфраструктуру времени выполнения для управления реляционными данными в виде объектов. В [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] модель данных реляционной базы данных сопоставляется объектной модели, выраженной в языке программирования разработчика. При выполнении приложения [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] преобразует интегрированные в язык запросы из объектной модели в SQL и отправляет их в базу данных для выполнения. Когда база данных возвращает результаты, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] переводит их обратно в объекты, которыми можно управлять.  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] включает поддержку хранимых процедур, определяемых пользователем функций в базе данных и наследования в объектной модели.  
  
 Дополнительные сведения см. в разделе [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 В модели [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)] реляционные данные представлены в виде объектов в среде .NET. Благодаря этому поддержка [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] эффективно реализуется на уровне объектов, что позволяет составлять запросы баз данных на языке, используемом для сборки бизнес-логики. Эта функция называется [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. Дополнительные сведения см. в разделе [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>См. также  
 [LINQ и ADO.NET](https://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec)  
 [Синтаксис LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
