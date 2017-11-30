---
title: ActivityTransfer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: acbc346da940caf933868a03295744132bda4733
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
