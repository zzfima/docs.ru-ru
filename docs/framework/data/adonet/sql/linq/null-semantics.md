---
title: Семантика NULL
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 3c4daa5fd37158f1af31f33ba743a56cf76670d8
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="null-semantics"></a>Семантика NULL
В следующей таблице приведены ссылки на различные части [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] документации где `null` (`Nothing` в Visual Basic) рассматриваются проблемы.  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Несоответствия типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|В разделе «Семантика со значениями Null» данного раздела рассматриваются три состояния SQL логическое сравнение двух состояний общеязыковая среда выполнения (CLR) <xref:System.Boolean>, литерал `Nothing` (Visual Basic) и `null` (C#) и другие аналогичные проблемы.|  
|[Преобразование стандартных операторов запросов](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|В подразделе "Семантика со значениями NULL" данного раздела описывается семантика сравнений со значением NULL в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
|[Методы System.String](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|В подразделе "Отличия от платформы .NET" данного раздела описывается, каким образом значение 0, возвращенное методом <xref:System.String.LastIndexOf%2A> , может означать, что строка равна значению NULL либо найденная позиция равна 0.|  
|[Вычисление суммы значений числовой последовательности](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|Описывает способ <xref:System.Linq.Enumerable.Sum%2A> оператор, результатом которого является `null` (`Nothing` в Visual Basic) вместо 0 для пустой последовательности или последовательности, содержащей только значения NULL.|  
  
## <a name="see-also"></a>См. также  
 [Типы данных и функции](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
