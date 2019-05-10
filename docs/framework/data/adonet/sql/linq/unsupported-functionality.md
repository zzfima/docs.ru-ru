---
title: Неподдерживаемые функциональные возможности
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: fb030a5f212be71d99b66f101e5e8411fbe4de33
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64618145"
---
# <a name="unsupported-functionality"></a>Неподдерживаемые функциональные возможности
В LINQ to SQL следующие функции SQL недоступны путем преобразования существующих конструкций среды CLR и .NET Framework.  
  
- `STDDEV`  
  
- `LIKE`  
  
     Хотя функция `LIKE` не поддерживается прямым преобразованием, аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>. Дополнительные сведения см. в разделе <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.  
  
- `DATEDIFF`  
  
     В LINQ to SQL реализована ограниченная поддержка функции `DATEDIFF`. Аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>.  
  
- `ROUND`  
  
     В LINQ to SQL реализована ограниченная поддержка функции `ROUND`. Дополнительные сведения см. в разделе [System.Math методы](system-math-methods.md).  
  
## <a name="see-also"></a>См. также

- [Типы данных и функции](data-types-and-functions.md)
