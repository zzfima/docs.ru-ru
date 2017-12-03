---
title: WSAT_TraceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b4e701c2f0d669a04be7f7235c8ab1edb8ce1612
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="wsattracerecord"></a>WSAT_TraceRecord
WSAT_TraceRecord  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс WSAT_TraceRecord не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс WSAT_TraceRecord имеет следующие свойства.  
  
### <a name="activityid"></a>ActivityID  
 Тип данных: объект  
Тип доступа: только для чтения  
  
 ИД активности записи трассировки.  
  
### <a name="eventid"></a>EventID  
 Тип данных: sint32  
Тип доступа: только для чтения  
  
 ИД события записи трассировки.  
  
### <a name="tracerecord"></a>TraceRecord  
 Тип данных: string  
Тип доступа: только для чтения  
  
 Запись трассировки  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|
