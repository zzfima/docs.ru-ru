---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: b1e5b87b053e947432cba9f6e716f7d1ea8f013f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation
Сопоставляет службу конечной точке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
