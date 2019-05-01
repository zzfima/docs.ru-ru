---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 3d23a3ee10c47e04ea7bdba202ea5063c0d84fac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62048235"
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
 Тип данных: Служба  
  
 Тип доступа: Только чтение  
Квалификаторы: Ключ  
  
 Служба, связанная с конечной точкой.  
  
### <a name="ref"></a>ref  
 Тип данных: Конечная точка  
  
 Тип доступа: Только чтение  
Квалификаторы: Ключ  
  
 Конечная точка, связанная со службой.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
