---
title: Методы System.Math
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: 0b113cefa6be040924134f9d2d0cb0c9d334feef
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792389"
---
# <a name="systemmath-methods"></a>Методы System.Math
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает следующие методы <xref:System.Math>.  
  
- <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a>Отличия от платформы .NET  
 Семантики округления в .NET Framework отличаются от подобных семантик SQL Server. Метод в .NET Framework выполняет *Округление банка*, где числа, заканчивающиеся на 0,5, округляются до ближайшей четной цифры, а не до следующей более высокой цифры. <xref:System.Math.Round%2A> Например, число 2,5 округляется до 2, а 3,5 - до 4. (Это помогает избежать систематического смещения в сторону более высоких значений в транзакциях данных.)  
  
 В SQL, наоборот, функция `ROUND` всегда округляет от нуля. Поэтому число 2,5 округляется до 3, тогда как в платформе .NET Framework - до 2.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] передается в семантики SQL `ROUND` и не пытается реализовать банковское округление.  
  
## <a name="see-also"></a>См. также

- [Типы данных и функции](data-types-and-functions.md)
