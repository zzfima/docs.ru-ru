---
title: Неподдерживаемые функциональные возможности
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: 5022c9011c2aac5b3272e359f991c40236a5673f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686708"
---
# <a name="unsupported-functionality"></a>Неподдерживаемые функциональные возможности
В LINQ to SQL следующие функции SQL недоступны путем преобразования существующих конструкций среды CLR и .NET Framework.  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     Хотя функция `LIKE` не поддерживается прямым преобразованием, аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>. Для получения дополнительной информации см. <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.  
  
-   `DATEDIFF`  
  
     В LINQ to SQL реализована ограниченная поддержка функции `DATEDIFF`. Аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>.  
  
-   `ROUND`  
  
     В LINQ to SQL реализована ограниченная поддержка функции `ROUND`. Дополнительные сведения см. в разделе [System.Math методы](system-math-methods.md).  
  
## <a name="see-also"></a>См. также
- [Типы данных и функции](data-types-and-functions.md)
