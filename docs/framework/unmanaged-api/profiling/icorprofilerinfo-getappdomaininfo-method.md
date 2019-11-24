---
title: Метод ICorProfilerInfo::GetAppDomainInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAppDomainInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetAppDomainInfo
helpviewer_keywords:
- ICorProfilerInfo::GetAppDomainInfo method [.NET Framework profiling]
- GetAppDomainInfo method [.NET Framework profiling]
ms.assetid: a6bf5a04-e03e-44f0-917a-96f6a6d3cc96
topic_type:
- apiref
ms.openlocfilehash: 8c13ce443037d706f9eba49760ba76f47c5a6538
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448175"
---
# <a name="icorprofilerinfogetappdomaininfo-method"></a>Метод ICorProfilerInfo::GetAppDomainInfo
Принимает идентификатор домена приложения. Возвращает имя домена приложения и идентификатор процесса, который его содержит.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetAppDomainInfo(  
    [in]  AppDomainID appDomainId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] ProcessID   *pProcessId);  
```  
  
## <a name="parameters"></a>Параметры  
 `appDomainId`  
 [in] Идентификатор домена приложения.  
  
 `cchName`  
 [in] Длина буфера возврата `szName` в символах.  
  
 `pcchName`  
 [out] Указатель на общую длину имени домена приложения в символах.  
  
 `szName`  
 [out] Буфер расширенных символов, предоставленный вызывающим объектом. При возврате метода параметр `szName` будет содержать полное или частичное имя домена приложения.  
  
 `pProcessId`  
 [out] Указатель на идентификатор процесса, который содержит этот домен приложения.  
  
## <a name="remarks"></a>Заметки  
 После возврата этого метода необходимо убедиться, что буфер `szName` был достаточно велик, чтобы вместить в себя полное имя домена приложения. Для этого сравните значение, на которое указывает параметр `pcchName`, со значением параметра `cchName`. Если параметр `pcchName` указывает на значение, превышающее значение `cchName`, выделите буфер `szName` большего размера, обновите параметр `cchName`, задав новый, больший размер, и вызовите метод `GetAppDomainInfo` снова.  
  
 Кроме того, сначала можно вызвать метод `GetAppDomainInfo` с буфером `szName` нулевой длины для получения правильного размера буфера. Затем можно задать размер буфера равным значению, возвращенному в параметре `pcchName`, и вызвать метод `GetAppDomainInfo` снова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
