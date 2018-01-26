---
title: "Неподдерживаемые функциональные возможности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b54bac0c9ce0b473ef8d86b039ef638b79af784f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="unsupported-functionality"></a>Неподдерживаемые функциональные возможности
В LINQ to SQL следующие функции SQL недоступны путем преобразования существующих конструкций среды CLR и .NET Framework.  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     Хотя функция `LIKE` не поддерживается прямым преобразованием, аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>. Для получения дополнительной информации см. <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.  
  
-   `DATEDIFF`  
  
     В LINQ to SQL реализована ограниченная поддержка функции `DATEDIFF`. Аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>.  
  
-   `ROUND`  
  
     В LINQ to SQL реализована ограниченная поддержка функции `ROUND`. Дополнительные сведения см. в разделе [методы System.Math](system-math-methods.md).  
  
## <a name="see-also"></a>См. также  
 [Типы данных и функции](data-types-and-functions.md)
