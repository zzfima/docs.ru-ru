---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 480670f19407321eb0928d07752936b2ece1f7e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="activitytransfer"></a>ActivityTransfer
Событие перенаправления действия  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс ActivityTransfer не определяет никакие методы.  
  
## <a name="properties"></a>Свойства  
 Класс ActivityTransfer имеет следующие свойства.  
  
### <a name="activityid"></a>ActivityID  
  
-   Тип данных: объект  
    Тип доступа: только для чтения  
  
-   Идентификатор действия  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
-   Тип данных: объект  
    Тип доступа: только для чтения  
  
-   Связанный идентификатор действия  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
