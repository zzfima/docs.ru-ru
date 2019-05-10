---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 6237d65d6964a4ebca34af895158c83239641593
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662814"
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
