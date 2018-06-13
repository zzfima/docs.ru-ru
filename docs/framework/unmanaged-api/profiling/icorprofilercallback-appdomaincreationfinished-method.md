---
title: Метод ICorProfilerCallback::AppDomainCreationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b0017cff43f7a1b1bdd90806f50abb374a96dadf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450428"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a>Метод ICorProfilerCallback::AppDomainCreationFinished
Уведомляет профилировщик, что домен приложения был создан.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
#### <a name="parameters"></a>Параметры  
 `appDomainId`  
 [in] Определяет домен, который был создан.  
  
 `hrStatus`  
 [in] Значение HRESULT, указывающее, успешно ли выполнено создание домена приложения.  
  
## <a name="remarks"></a>Примечания  
 Идентификатор приложения является недопустимым для любого запроса информации до `AppDomainCreationFinished` вызывается метод.  
  
 Некоторые части загрузки домена приложения может быть продолжено после `AppDomainCreationFinished` обратного вызова. Значение HRESULT в `hrStatus` указывает на сбой. Тем не менее значение HRESULT в `hrStatus` указывает, что первая часть создания домена приложения выполнено успешно.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
