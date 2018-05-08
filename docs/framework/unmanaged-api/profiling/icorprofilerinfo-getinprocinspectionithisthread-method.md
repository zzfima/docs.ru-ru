---
title: Метод ICorProfilerInfo::GetInprocInspectionIThisThread
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6d603d9bc7a343a41224cf8d889a69823875d9db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a>Метод ICorProfilerInfo::GetInprocInspectionIThisThread
Возвращает объект, который может запрашиваться для ICorDebugThread-интерфейс. Этот метод является устаревшим в .NET Framework версии 2.0.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppicd`  
 [out](/cpp/atl/iunknown) объекта, который может запрашиваться для `ICorDebugThread` интерфейса.  
  
## <a name="remarks"></a>Примечания  
 Общеязыковой среды выполнения (CLR), службами отладки поддерживается только в процессе отладки в .NET Framework версии 1.0. Внутрипроцессная отладка позволяла профилировщику использовать проверочную API отладки. В результате отзывов клиентов внутрипроцессная отладка были удалены из .NET Framework версии 2.0 и заменена набором функциональных возможностей, которые лучше подходят для API профилирования.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версия платформы .NET framework:** 1.0  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
