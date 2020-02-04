---
title: Метод ICorProfilerInfo::EndInprocDebugging
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.EndInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type:
- apiref
ms.openlocfilehash: 8a15843e9169442d89996375ee85f62b38f92e30
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864262"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a>Метод ICorProfilerInfo::EndInprocDebugging
Завершает работу внутрипроцессного сеанса отладки. Этот метод является устаревшим в .NET Framework версии 2,0.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwProfilerContext`  
 окне Значение, идентифицирующее сеанс отладки. Это значение должно совпадать со значением, полученным в методе [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) .  
  
## <a name="remarks"></a>Заметки  
 Необходимо вызвать метод [ICorProfilerInfo:: BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md) и `EndInprocDebugging` в том же методе обратного вызова.  
  
 Службы отладки CLR поддерживали ограниченную внутрипроцессную отладку в .NET Framework версиях 1,0 и 1,1. В процессе отладки с помощью профилировщика можно использовать части проверки для API отладки. Однако из-за отзывов клиентов внутрипроцессный процесс отладки был удален из .NET Framework в версии 2,0 и заменен набором функциональных возможностей, которые более подробно описаны в API профилирования.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версия .NET Framework:** 1,0  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
