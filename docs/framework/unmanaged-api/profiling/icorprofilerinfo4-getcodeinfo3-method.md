---
title: Метод ICorProfilerInfo4::GetCodeInfo3
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 084007bd7ab20449c28d2c5e6125cbacfa280526
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912717"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a>Метод ICorProfilerInfo4::GetCodeInfo3
Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionID`  
 [in] Идентификатор функции, с которым связан машинный код.  
  
 `reJitId`  
 [in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора.  
  
 `cCodeInfos`  
 [in] Размер массива `codeInfos`.  
  
 `pcCodeInfos`  
 заполняет Указатель на общее число доступных структур [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) .  
  
 `codeInfos`  
 [out] Буфер, предоставляемый вызывающим объектом. После возврата метода он содержит массив структур `COR_PRF_CODE_INFO`, каждая из которых описывает блок машинного кода.  
  
## <a name="remarks"></a>Примечания  
 Метод `GetCodeInfo3` аналогичен [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), за исключением того, что он получает JIT-перекомпилированный идентификатор функции, которая содержит указанный IP-адрес.  
  
> [!NOTE]
> `GetCodeInfo3`может запустить сборку мусора, в то время как [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) не будет. Дополнительные сведения см. в описании HRESULT [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) .  
  
 Расширения сортируются в порядке возрастания смещения общих промежуточного языка (CIL).  
  
 После `GetCodeInfo3` возврата необходимо убедиться `codeInfos` , что буфер достаточно велик, чтобы вместить все структуры [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) . Для этого сравните значение параметра `cCodeInfos` со значением параметра `cchName`. При `cCodeInfos` делении на размер `pcCodeInfos`структуры [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) меньше, выделяет буфер большего `codeInfos` размера, обновляет `cCodeInfos` новый, больший размер и вызывается `GetCodeInfo3` снова.  
  
 Кроме того, сначала можно вызвать метод `GetCodeInfo3` с буфером `codeInfos` нулевой длины для получения правильного размера буфера. Затем можно `codeInfos` задать размер буфера равным значению, возвращенному `pcCodeInfos`в, умноженному на размер структуры [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) и вызывать `GetCodeInfo3` повторно.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf. idl, CorProf. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)
- [Интерфейс ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
