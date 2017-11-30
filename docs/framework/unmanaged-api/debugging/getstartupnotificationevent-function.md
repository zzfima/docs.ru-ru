---
title: "Функция GetStartupNotificationEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetStartupNotificationEvent
api_location: dbgshim.dll
api_type: COM
f1_keywords: GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 305350a9186c90af1e8646bc230536dcd2de47cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="getstartupnotificationevent-function"></a>Функция GetStartupNotificationEvent
Создает или открывает обработчик событий, который будет информироваться любой средой CLR, загружаемой в указанный целевой процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
#### <a name="parameters"></a>Параметры  
 `debuggeePID`  
 [in] Идентификатор целевого процесса, из которого следует получать уведомления при запуске среды CLR.  
  
 `phStartupEvent`  
 [out] Указатель на дескриптор, который будет оповещаться средой CLR при запуске.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Успешно получен дескриптор события уведомления при запуске.  
  
 E_INVALIDARG  
 `phStartupEvent` имеет значение null, или `debuggeePID` не ссылается на процесс, выполняющийся в текущий момент.  
  
 E_FAIL (или другие коды возврата E_)  
 Не удалось получить дескриптор события уведомления при запуске.  
  
## <a name="remarks"></a>Примечания  
 В операционной системе Windows `debuggeePID` сопоставляется с идентификатором процесса ОС.  
  
 Событие сигнализирует перед любым выполнением управляемого кода средой CLR, которая оповещает событие.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** dbgshim.h  
  
 **Библиотека:** dbgshim.dll  
  
 **Версии платформы .NET framework:** 3.5 SP1
