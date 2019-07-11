---
title: Метод ICorProfilerInfo::GetModuleMetaData
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e63cf698e41e70084c9b71bdf58d7ac60723d53
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782788"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>Метод ICorProfilerInfo::GetModuleMetaData
Получает экземпляр интерфейса метаданных, который сопоставляется указанного модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleId`  
 [in] Идентификатор модуля, с которым будет сопоставлен экземпляр интерфейса.  
  
 `dwOpenFlags`  
 [in] Значение [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) перечисления, указывающее режим для открытия файлов манифеста. Только `ofRead`, `ofWrite` и `ofNoTransform` bits являются допустимыми.  
  
 `riid`  
 [in] Ссылка на идентификатор (GUID) интерфейс метаданных, экземпляр которого будут извлекаться. См. в разделе [интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) список интерфейсов.  
  
 `ppOut`  
 [out] Указатель на адрес метаданных экземпляра интерфейса.  
  
## <a name="remarks"></a>Примечания  
 Существует возможность запросить метаданные для открытия в режиме чтения/записи, но это приведет к замедлению выполнения программы, поскольку изменения метаданных не могут быть оптимизированы, как от компилятора.  
  
 Некоторые модули (например, модули ресурсов) имеют без метаданных. В таком случае `GetModuleMetaData` возвратит значение HRESULT S_FALSE, и значение null в *`ppOut`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
