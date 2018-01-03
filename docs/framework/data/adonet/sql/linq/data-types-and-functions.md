---
title: "Типы данных и функции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 683413c5-0312-4e60-8619-9a97bdc6e62a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: af102a0d6ca8ec1092c8b0909a7817cb053ab6c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="data-types-and-functions"></a>Типы данных и функции
Перечисленные в следующей таблице разделы описывают поддержку в LINQ to SQL элементов, конструкций и приведения среды CLR. Поддерживаемые элементы и конструкции доступны для использования в запросах LINQ to SQL.  
  
 Если в таблице элемент отмечен как неподдерживаемый, то LINQ to SQL не может перевести этот элемент, конструкцию или приведение типов среды CLR для выполнения на SQL Server. Их по-прежнему можно использовать в коде, но вычислять их следует или до преобразования запроса в Transact-SQL, или после получения результатов из базы данных.  
  
|Раздел|Описание:|  
|-----------|-----------------|  
|[Сопоставление типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)|Содержит таблицу с подробными сведениями о сопоставлении между типами CLR и типами SQL Server.|  
|[Базовые типы данных](../../../../../../docs/framework/data/adonet/sql/linq/basic-data-types.md)|Обобщены различия в поведении относительно платформы [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].|  
|[Логические типы данных](../../../../../../docs/framework/data/adonet/sql/linq/boolean-data-types.md)|Обобщены различия в поведении относительно платформы [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].|  
|[Семантика NULL](../../../../../../docs/framework/data/adonet/sql/linq/null-semantics.md)|Приведены ссылки на разделы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], посвященные обсуждению значений NULL и связанных с ними вопросов.|  
|[Числовые операторы и операторы сравнения](../../../../../../docs/framework/data/adonet/sql/linq/numeric-and-comparison-operators.md)|Обобщены различия в поведении относительно платформы [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].|  
|[Операторы последовательности](../../../../../../docs/framework/data/adonet/sql/linq/sequence-operators.md)|Обобщены различия в поведении относительно платформы [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].|  
|[Методы System.Convert](../../../../../../docs/framework/data/adonet/sql/linq/system-convert-methods.md)|Обобщены различия в поведении относительно платформы [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].|  
|[Методы System.DateTime](../../../../../../docs/framework/data/adonet/sql/linq/system-datetime-methods.md)|Описана поддержка в LINQ to SQL элементов структуры <xref:System.DateTime?displayProperty=nameWithType>.|  
|[Методы System.DateTimeOffset](../../../../../../docs/framework/data/adonet/sql/linq/system-datetimeoffset-methods.md)|Описана поддержка в LINQ to SQL элементов структуры <xref:System.DateTimeOffset?displayProperty=nameWithType>.|  
|[Методы System.Math](../../../../../../docs/framework/data/adonet/sql/linq/system-math-methods.md)|Обобщены различия в поведении относительно платформы [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].|  
|[Методы System.Object](../../../../../../docs/framework/data/adonet/sql/linq/system-object-methods.md)|Обобщены различия в поведении относительно платформы [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].|  
|[Методы System.String](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|Обобщены различия в поведении относительно платформы [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].|  
|[Методы System.TimeSpan](../../../../../../docs/framework/data/adonet/sql/linq/system-timespan-methods.md)|Описана поддержка в LINQ to SQL элементов структуры <xref:System.TimeSpan?displayProperty=nameWithType>.|  
|[Неподдерживаемые функциональные возможности](../../../../../../docs/framework/data/adonet/sql/linq/unsupported-functionality.md)|Описаны функции, которые не поддерживаются в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
  
## <a name="see-also"></a>См. также  
 [Несоответствия типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)  
 [Ссылки](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [Библиотека классов .NET framework в Visual Studio](http://msdn.microsoft.com/en-us/a03e374c-3d5c-4169-937b-49857ab273ae)
