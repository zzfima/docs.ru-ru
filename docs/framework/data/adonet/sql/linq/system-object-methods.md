---
title: Методы System.Object
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: 3a52f081f1c0c6e6c5218550009c736d0ed60514
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097672"
---
# <a name="systemobject-methods"></a>Методы System.Object
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает следующие <xref:System.Object> методы.  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает следующие <xref:System.Object> методы.  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType> для двоичных типов, таких как `BINARY`, `VARBINARY`, `IMAGE`, и `TIMESTAMP`.||  
  
## <a name="differences-from-net"></a>Отличия от платформы .NET  
 Выходные данные <xref:System.Object.ToString?displayProperty=nameWithType> для double используется SQL `CONVERT`(NVARCHAR(30), @x, 2) на SQL Server. В этом случае SQL всегда использует 16 цифр и экспоненциальный формат (например, «0.000000000000000e+000» для 0). В результате преобразование <xref:System.Object.ToString?displayProperty=nameWithType> формирует строку, отличную от строки преобразования <xref:System.Convert.ToString%2A?displayProperty=nameWithType> на платформе .NET Framework.  
  
## <a name="see-also"></a>См. также

- [Типы данных и функции](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
