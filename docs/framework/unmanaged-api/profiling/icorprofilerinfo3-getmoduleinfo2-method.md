---
title: ICorProfilerInfo3::GetModuleInfo2 Method
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetModuleInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetModuleInfo2
helpviewer_keywords:
- ICorProfilerInfo3::GetModuleInfo2 method [.NET Framework profiling]
- GetModuleInfo2 method [.NET Framework profiling]
ms.assetid: f1f6b8f3-dcfc-49e8-be76-ea50ea90d5a7
topic_type:
- apiref
ms.openlocfilehash: 96cde35c7151bb7ce58715f2826feaa59b30efab
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862312"
---
# <a name="icorprofilerinfo3getmoduleinfo2-method"></a>ICorProfilerInfo3::GetModuleInfo2 Method
Возвращает имя файла модуля, идентификатор родительской сборки модуля и битовую маску, описывающую свойства модуля, по идентификатору модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetModuleInfo2(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, annotation("__out_ecount_part(cchName, *pcchName)")]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
    [out] DWORD                 *pdwModuleFlags);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleId`  
 [in] Идентификатор модуля, для которого будут извлекаться сведения.  
  
 `ppBaseLoadAddress`  
 [out] Базовый адрес, по которому модуль был загружен.  
  
 `cchName`  
 [in] Длина буфера возврата `szName` в символах.  
  
 `pcchName`  
 [out] Указатель на общую длину возвращаемого имени файла модуля в символах.  
  
 `szName`  
 [out] Буфер расширенных символов, предоставленный вызывающим объектом. При возврате метода этот буфер содержит имя файла модуля.  
  
 `pAssemblyId`  
 [out] Указатель на идентификатор родительской сборки модуля.  
  
 `pdwModuleFlags`  
 заполняет Битовая маска значений из перечисления [COR_PRF_MODULE_FLAGS](cor-prf-module-flags-enumeration.md) , определяющая свойства модуля.  
  
## <a name="remarks"></a>Заметки  
 Для динамических модулей параметр `szName` является именем метаданных модуля, а базовый адрес равен 0 (нулю). Имя метаданных — это значение в столбце Name таблицы Module в метаданных. Это также предоставляется в качестве свойства <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> для управляемого кода, а также в качестве параметра `szName` метода [IMetaDataImport:: жетскопепропс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) в неуправляемый клиентский код метаданных.  
  
 Несмотря на то, что метод `GetModuleInfo2` может вызываться сразу после существования идентификатора модуля, идентификатор родительской сборки будет недоступен до тех пор, пока профилировщик не получит обратный вызов [ICorProfilerCallback:: модулеаттачедтоассембли](icorprofilercallback-moduleattachedtoassembly-method.md) .  
  
 После возврата метода `GetModuleInfo2` необходимо убедиться, что буфер `szName` был достаточно велик, чтобы вместить в себя полное имя файла модуля. Для этого сравните значение, на которое указывает параметр `pcchName`, со значением параметра `cchName`. Если параметр `pcchName` указывает на значение, превышающее значение `cchName`, выделите буфер `szName` большего размера, обновите параметр `cchName`, задав новый, больший размер, и вызовите метод `GetModuleInfo2` снова.  
  
 Кроме того, сначала можно вызвать метод `GetModuleInfo2` с буфером `szName` нулевой длины для получения правильного размера буфера. Затем можно задать размер буфера равным значению, возвращенному в параметре `pcchName`, и вызвать метод `GetModuleInfo2` снова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейсы профилирования](profiling-interfaces.md)
- [Профилирование](index.md)
