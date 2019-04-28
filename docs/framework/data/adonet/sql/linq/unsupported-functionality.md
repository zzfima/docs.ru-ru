---
title: Неподдерживаемые функциональные возможности
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: 18a1a8f33a9360b4299648bcd329f4c5f2e7de88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917562"
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
