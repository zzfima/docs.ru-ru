---
title: Метод ICorProfilerInfo::GetAssemblyInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAssemblyInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyInfo Method
helpviewer_keywords:
- GetAssemblyInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetAssemblyInfo method [.NET Framework profiling]
ms.assetid: 7a3c97c3-1e31-47b1-bf23-386785c509c4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b410ef46e96f75d98ee750c760b19d2a77eec2b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780218"
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a>Метод ICorProfilerInfo::GetAssemblyInfo
Принимает идентификатор сборки и возвращает имя сборки, а также идентификатор ее модуля манифеста.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetAssemblyInfo(  
    [in]  AssemblyID  assemblyId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] AppDomainID *pAppDomainId,  
    [out] ModuleID    *pModuleId);  
```  
  
## <a name="parameters"></a>Параметры  
 `assemblyId`  
 [in] Идентификатор сборки.  
  
 `cchName`  
 [in] Длина `szName` в символах.  
  
 `pcchName`  
 [out] Указатель на общую длину имени сборки в символах.  
  
 `szName`  
 [out] Буфер расширенных символов, предоставленный вызывающим объектом. Когда функция возвращает значение, оно содержит имя сборки.  
  
 `pAppDomainId`  
 [out] Указатель на идентификатор домена приложения, содержащего эту сборку.  
  
 `pModuleId`  
 [out] Указатель на идентификатор модуля манифеста сборки.  
  
## <a name="remarks"></a>Примечания  
 После возврата этого метода необходимо убедиться, что буфер `szName` был достаточно велик, чтобы вместить в себя полное имя сборки. Для этого сравните значение, на которое указывает параметр `pcchName`, со значением параметра `cchName`. Если параметр `pcchName` указывает на значение, превышающее значение `cchName`, выделите буфер `szName` большего размера, обновите параметр `cchName`, задав новый, больший размер, и вызовите метод `GetAssemblyInfo` снова.  
  
 Кроме того, сначала можно вызвать метод `GetAssemblyInfo` с буфером `szName` нулевой длины для получения правильного размера буфера. Затем можно настроить размер буфера, исходя из значения, возвращенного в `pcchName`, и вызвать метод `GetAssemblyInfo` снова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
