---
title: 'ICorProfilerInfo9:: Жетнативекодестартаддрессес'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f5c7f11a322e4cf3ed38608e0f380dd632bc8fb6
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973814"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a>Метод ICorProfilerInfo9:: Жетнативекодестартаддрессес
  
 При наличии кода functionId и Режитид перечисляются начальные адреса всех откомпилированных версий этого кода, которые в настоящее время существуют.   
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```  
  
#### <a name="parameters"></a>Параметры  
 `functionId`  
 окне Идентификатор функции, для которой должны возвращаться начальные адреса машинного кода.  
  
 `reJitId`  
 [in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора. 
  
 `cCodeStartAddresses` \
 [in] Максимальный размер массива `codeStartAddresses`.

 `pcCodeStartAddresses` \
 заполняет Количество доступных адресов.

 `codeStartAddresses` \
 заполняет Массив `UINT_PTR`, каждый из которых является начальным адресом для заданной функции в машинном тексте. 

## <a name="remarks"></a>Примечания  
 Если включена многоуровневая компиляция, функция может иметь более одного тела машинного кода. 

## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).  
  
 **Заголовок.** CorProf. idl, CorProf. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)] 
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)

