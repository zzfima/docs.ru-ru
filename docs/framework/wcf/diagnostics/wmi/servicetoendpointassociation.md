---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 3d23a3ee10c47e04ea7bdba202ea5063c0d84fac
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372191"
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation
Сопоставляет службу конечной точке.  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс ServiceToEndpointAssociation не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс ServiceToEndpointAssociation имеет следующие свойства.  
  
### <a name="ref"></a>ref  
 Тип данных: Service  
  
 Тип доступа: только для чтения  
Квалификаторы: ключ  
  
 Служба, связанная с конечной точкой.  
  
### <a name="ref"></a>ref  
 Тип данных: Endpoint  
  
 Тип доступа: только для чтения  
Квалификаторы: ключ  
  
 Конечная точка, связанная со службой.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
