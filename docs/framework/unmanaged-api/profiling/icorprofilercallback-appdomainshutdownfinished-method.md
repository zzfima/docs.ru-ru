---
title: Метод ICorProfilerCallback::AppDomainShutdownFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
ms.openlocfilehash: 0851ac33a2bac4fcf727cf09e5225f6b83481b50
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866680"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a>Метод ICorProfilerCallback::AppDomainShutdownFinished
Уведомляет профилировщик о том, что домен приложения был выгружен из процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>Параметры

- `appDomainId`

  \[в] определяет домен, в котором хранятся сборки приложения.

- `hrStatus`

  \[in] значение HRESULT, указывающее, успешно ли выгружен домен приложения.

## <a name="remarks"></a>Заметки  
 Значение `appDomainId` недопустимо для информационного запроса после возврата метода [ICorProfilerCallback:: AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) .  
  
 Некоторые части выгрузки домена приложения могут продолжаться после обратного вызова `AppDomainCreationFinished`. Ошибка HRESULT в `hrStatus` указывает на сбой. Однако значение HRESULT успешного выполнения в `hrStatus` указывает, что первая часть выгрузки домена приложения успешно выполнена.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
