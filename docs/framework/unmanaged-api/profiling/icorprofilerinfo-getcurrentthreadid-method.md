---
title: Метод ICorProfilerInfo::GetCurrentThreadID
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
ms.openlocfilehash: e70d8ee40e16e37a12f8ed4033d2aa7489f0f25e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863965"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a>Метод ICorProfilerInfo::GetCurrentThreadID
Возвращает идентификатор текущего потока, если он является управляемым потоком.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a>Параметры  
 `pThreadId`  
 заполняет Указатель на возвращенный идентификатор управляемого потока.  
  
## <a name="remarks"></a>Заметки  
 Если текущий поток является внутренним потоком среды выполнения или другим неуправляемым потоком, `GetCurrentThreadID` возвращает CORPROF_E_NOT_MANAGED_THREAD как HRESULT, а возвращаемое значение параметра `pThreadId` будет равно null.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
