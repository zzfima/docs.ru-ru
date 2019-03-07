---
title: Метод ICorProfilerInfo2::GetContextStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16390317f8a6ea1ee9a3841e35b32e040d12db5d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485126"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a>Метод ICorProfilerInfo2::GetContextStaticAddress
Возвращает адрес для указанного поля статического контекста, в рамках заданного контекста.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Параметры  
 `classId`  
 [in] Идентификатор класса, содержащего запрошенного контекстно статические поля.  
  
 `fieldToken`  
 [in] Маркер метаданных для запрошенного статического поля контекста.  
  
 `contextId`  
 [in] Идентификатор контекста, который является областью для запрошенного статического поля контекста.  
  
 `ppAddress`  
 [out] Указатель на адрес статического поля, в заданном контексте.  
  
## <a name="remarks"></a>Примечания  
 `GetContextStaticAddress` Метод может возвращать одно из следующих:  
  
-   HRESULT CORPROF_E_DATAINCOMPLETE, если заданного статические поля не был назначен адрес в заданном контексте.  
  
-   Адреса объектов, которые могут быть в куче сбора мусора. Эти адреса могут стать недопустимыми после сборки мусора, поэтому после сборки мусора, профилировщики не следует предполагать, что они являются допустимыми.  
  
 До завершения конструктора класса `GetContextStaticAddress` возвращает CORPROF_E_DATAINCOMPLETE для всех статических полей, несмотря на то, что некоторые статические поля уже могут быть инициализированы и болея объекты сборки мусора.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
