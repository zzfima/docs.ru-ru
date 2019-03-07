---
title: Метод ICorProfilerInfo4::GetILToNativeMapping2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetILToNativeMapping2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2
helpviewer_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2 method [.NET Framework profiling]
- GetILToNativeMapping2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 756c1c25-08a7-4060-9798-dbeaa2f3bee5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7124aadc9c848ee2656473b7e06c3bc9b7881a2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469340"
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a>Метод ICorProfilerInfo4::GetILToNativeMapping2
Получает сопоставление из смещений MSIL в собственные смещения для кода, содержащегося в версии указанной функции, перекомпилированной с помощью JIT-компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 [in] Идентификатор функции, которая содержит код.  
  
 `pReJitId`  
 [in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора. Удостоверение должно быть равно нулю в [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].  
  
 `cMap`  
 [in] Максимальный размер массива `map`.  
  
 `pcMap`  
 [out] Общее число доступных структур COR_DEBUG_IL_TO_NATIVE_MAP.  
  
 `map`  
 [out] Массив структур `COR_DEBUG_IL_TO_NATIVE_MAP`, каждая из которых задает смещения. После возврата метода `GetILToNativeMapping2` параметр `map` будет содержать все или некоторые из структур `COR_DEBUG_IL_TO_NATIVE_MAP`.  
  
## <a name="remarks"></a>Примечания  
 `GetILToNativeMapping2` аналогичен [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) метода, за исключением того, что он позволяет профилировщику указывать идентификатор перекомпилированной функции в будущих выпусках.  
  
> [!NOTE]
>  [ICorProfilerFunctionControl::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) метод не реализован в [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], поэтому функции, которые были перекомпиляции JIT не могут иметь сопоставление IL-машинный код, который отличается от изначально скомпилирована функция. Таким образом, в [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] метод `GetILToNativeMapping2` не может вызываться с ненулевым идентификатором функции, перекомпилированной с помощью JIT-компилятора.  
  
 Метод `GetILToNativeMapping2` возвращает массив структур `COR_DEBUG_IL_TO_NATIVE_MAP`. Для передачи, что определенные диапазоны собственных инструкций соответствуют специальным областям кода (например, прологу), запись в массиве может иметь его `ilOffset` полю присвоено значение [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) перечисление.  
  
 После возврата метода `GetILToNativeMapping2` необходимо убедиться, что буфер `map` был достаточно велик, чтобы вместить в себя все структуры `COR_DEBUG_IL_TO_NATIVE_MAP`. Для этого сравните значение параметра `cMap` со значением параметра `pcMap`. Если значение `pcMap`, умноженное на размер структуры `COR_DEBUG_IL_TO_NATIVE_MAP`COR_PRF_CODE_INFO, больше значения `cMap`, выделите буфер `map` большего размера, обновите параметр `cMap`, задав новый, больший размер, и вызовите метод `GetILToNativeMapping2` снова.  
  
 Кроме того, сначала можно вызвать метод `GetILToNativeMapping2` с буфером `map` нулевой длины для получения правильного размера буфера. Затем можно задать размер буфера равным значению, возвращенному в параметре `pcMap`, и вызвать метод `GetILToNativeMapping2` снова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Метод GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [Интерфейс ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
