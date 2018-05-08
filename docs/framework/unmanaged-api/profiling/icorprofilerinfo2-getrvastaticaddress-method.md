---
title: Метод ICorProfilerInfo2::GetRVAStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ee12131cfa323d4426ab06ea31be4a8dd7b4583
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a>Метод ICorProfilerInfo2::GetRVAStaticAddress
Возвращает адрес указанного относительного виртуального адреса (RVA) статического поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a>Параметры  
 `classId`  
 [in] Идентификатор класса, содержащего запрашиваемого RVA статического поля.  
  
 `fieldToken`  
 [in] Токен метаданных для запрошенного RVA статического поля.  
  
 `ppAddress`  
 [out] Указатель на адрес RVA статического поля.  
  
## <a name="remarks"></a>Примечания  
 `GetRVAStaticAddress` Метод может возвращать одно из следующих действий:  
  
-   CORPROF_E_DATAINCOMPLETE HRESULT, если заданного статического поля не был назначен адрес в указанном контексте.  
  
-   Адреса объектов, которые могут находиться в куче сборщика мусора. Эти адреса могут стать недопустимыми после сборки мусора, поэтому после сборки мусора профилировщики не следует предполагать, что они являются допустимыми.  
  
 До завершения конструктора класса `GetRVAStaticAddress` возвращает CORPROF_E_DATAINCOMPLETE для всех статических полей, хотя некоторые статические поля уже могут быть инициализированы и могут маршрутизировать объекты сборки мусора.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
