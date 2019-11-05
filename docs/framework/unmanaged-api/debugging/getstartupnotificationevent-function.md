---
title: Функция GetStartupNotificationEvent
ms.date: 03/30/2017
api_name:
- GetStartupNotificationEvent
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type:
- apiref
ms.openlocfilehash: fb158b35165fb229fc78169e2508679b6749752e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122955"
---
# <a name="getstartupnotificationevent-function"></a>Функция GetStartupNotificationEvent
Создает или открывает обработчик событий, который будет информироваться любой средой CLR, загружаемой в указанный целевой процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a>Параметры  
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
  
## <a name="remarks"></a>Заметки  
 В операционной системе Windows `debuggeePID` сопоставляется с идентификатором процесса ОС.  
  
 Событие сигнализирует перед любым выполнением управляемого кода средой CLR, которая оповещает событие.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** dbgshim. h  
  
 **Библиотека:** dbgshim. dll  
  
 **.NET Framework версии:** 3,5 SP1
