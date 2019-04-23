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
ms.openlocfilehash: ad4ebe4e1255ce13974063eef3d0a4feeb5dd92b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083062"
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a>Метод ICorProfilerInfo::GetAssemblyInfo
Принимает идентификатор сборки и возвращает имя сборки, а также идентификатор ее модуля манифеста.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
