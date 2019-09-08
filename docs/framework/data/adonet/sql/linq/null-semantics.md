---
title: Семантика NULL
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: d0b18c0a699840d11f5e4add05147672f9bb69e9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792978"
---
# <a name="null-semantics"></a>Семантика NULL
В следующей таблице приведены ссылки на различные части [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] документации, где `null` обсуждаются`Nothing` проблемы (в Visual Basic).  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Несоответствия типов SQL-CLR](sql-clr-type-mismatches.md)|В подразделе "семантика со значениями NULL" <xref:System.Boolean>этого раздела содержится обсуждение логического состояния SQL, основанного на трех и двух состоянийх, литерал `Nothing` (Visual Basic) и `null` (C#) и другие аналогичные проблем.|  
|[Преобразование стандартных операторов запросов](standard-query-operator-translation.md)|В подразделе "Семантика со значениями NULL" данного раздела описывается семантика сравнений со значением NULL в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
|[Методы System.String](system-string-methods.md)|В подразделе "Отличия от платформы .NET" данного раздела описывается, каким образом значение 0, возвращенное методом <xref:System.String.LastIndexOf%2A> , может означать, что строка равна значению NULL либо найденная позиция равна 0.|  
|[Вычисление суммы значений числовой последовательности](compute-the-sum-of-values-in-a-numeric-sequence.md)|Описывает, как <xref:System.Linq.Enumerable.Sum%2A> оператор вычисляет `null` значение (`Nothing` в Visual Basic) вместо 0 для последовательности, содержащей только значения NULL или для пустой последовательности.|  
  
## <a name="see-also"></a>См. также

- [Типы данных и функции](data-types-and-functions.md)
