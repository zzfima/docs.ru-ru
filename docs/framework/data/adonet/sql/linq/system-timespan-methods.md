---
title: "Методы System.TimeSpan"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9333fee8-1454-4374-855b-8c14c002f48f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a32b57488b49e9fd2f4e6342391690b27d7ad825
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="systemtimespan-methods"></a>Методы System.TimeSpan
Поддержка элементов типа <xref:System.TimeSpan?displayProperty=nameWithType> в значительной степени зависит от используемых версий платформы .NET Framework и сервера Microsoft SQL Server.  
  
 Если метод, оператор или свойство не поддерживаются, это означает, что LINQ to SQL не может перевести элемент для выполнения на SQL Server. Но эти элементы, тем не менее, можно использовать в коде. Однако их следует вычислять до преобразования запроса в Transact-SQL или после получения результатов из базы данных.  
  
## <a name="previous-limitations"></a>Предыдущие ограничения  
 При использовании LINQ to SQL с версиями платформы .NET Framework, выпущенными до .NET Framework 3.5 с пакетом обновления 1 (SP1), невозможно сопоставлять поля баз данных SQL Server типу <xref:System.TimeSpan?displayProperty=nameWithType>. При этом операции с типом <xref:System.TimeSpan> поддерживаются, поскольку значения <xref:System.TimeSpan> могут возвращаться операцией вычитания <xref:System.DateTime> или входить в выражение в виде литерала или привязанной переменной.  
  
## <a name="supported-systemtimespan-method-support"></a>Поддержка поддерживаемого метода System.TimeSpan  
 Следующие поддерживаемые в LINQ to SQL методы, операторы и свойства доступны для использования в запросах LINQ to SQL. После их сопоставления в модели объектов или внешнем файле сопоставления LINQ to SQL позволяет использовать многие элементы <xref:System.TimeSpan?displayProperty=nameWithType> внутри запросов LINQ to SQL.  
  
|Поддерживаемые методы <xref:System.TimeSpan>|Поддерживаемые операторы <xref:System.TimeSpan>|Поддерживаемые свойства <xref:System.TimeSpan>|  
|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.TimeSpan.Compare%2A>|<xref:System.TimeSpan.op_Equality%2A>|<xref:System.TimeSpan.Days%2A>|  
|<xref:System.TimeSpan.CompareTo%28System.TimeSpan%29>|<xref:System.TimeSpan.op_GreaterThan%2A>|<xref:System.TimeSpan.Hours%2A>|  
|<xref:System.TimeSpan.Duration%2A>|<xref:System.TimeSpan.op_GreaterThanOrEqual%2A>|<xref:System.TimeSpan.MaxValue>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%2CSystem.TimeSpan%29>|<xref:System.TimeSpan.op_Inequality%2A>|<xref:System.TimeSpan.Milliseconds%2A>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%29>|<xref:System.TimeSpan.op_LessThan%2A>|<xref:System.TimeSpan.Minutes%2A>|  
||<xref:System.TimeSpan.op_LessThanOrEqual%2A>|<!--zz <xref:System.TimeSpan.MinValue%2A>-->|  
  
> [!NOTE]
>  Чтобы сопоставлять тип <xref:System.TimeSpan?displayProperty=nameWithType> со столбцами SQL типа `TIME` с помощью LINQ to SQL, необходима платформа .NET Framework 3.5 с пакетом обновления 1 (SP1) и более поздней версии. Тип данных SQL `TIME` доступен только в версиях Microsoft SQL Server 2008 и выше.  
  
### <a name="addition-and-subtraction"></a>Сложение и вычитание  
 Хотя тип CLR <xref:System.TimeSpan?displayProperty=nameWithType> поддерживает сложение и вычитание, тип SQL `TIME` их не поддерживает. Поэтому запросы LINQ to SQL будут вызывать ошибки при попытке выполнить сложение или вычитание, когда они сопоставлены с типом SQL `TIME`. Можно найти дополнительные сведения о работе с типами даты и времени SQL в [сопоставление типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
## <a name="see-also"></a>См. также  
 [Основные принципы запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [Создание модели объектов](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [Сопоставление типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)  
 [Типы данных и функции](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
