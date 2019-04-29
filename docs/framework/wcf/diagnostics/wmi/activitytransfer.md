---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964299"
---
# <a name="activitytransfer"></a>ActivityTransfer
Событие перенаправления действия  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
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
  
- Тип данных: объект  
    Тип доступа: Только чтение  
  
- ИД действия  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
- Тип данных: объект  
    Тип доступа: Только чтение  
  
- Связанный идентификатор действия  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
