---
title: Методы System.Math
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: 1dae31b30962505c07c198f3bd35fceb8f400efb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917687"
---
# <a name="systemmath-methods"></a>Методы System.Math
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает следующие методы <xref:System.Math>.  
  
- <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a>Отличия от платформы .NET  
 Семантики округления в .NET Framework отличаются от подобных семантик SQL Server. <xref:System.Math.Round%2A> В .NET Framework выполняет *банковское округление*, где числа, оканчивающиеся на.5 округление до ближайшего четного числа, а не для ближайшего большего числа. Например, число 2,5 округляется до 2, а 3,5 - до 4. (Это помогает избежать систематического смещения в сторону более высоких значений в транзакциях данных.)  
  
 В SQL, наоборот, функция `ROUND` всегда округляет от нуля. Поэтому число 2,5 округляется до 3, тогда как в платформе .NET Framework - до 2.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] передается в семантики SQL `ROUND` и не пытается реализовать банковское округление.  
  
## <a name="see-also"></a>См. также

- [Типы данных и функции](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
