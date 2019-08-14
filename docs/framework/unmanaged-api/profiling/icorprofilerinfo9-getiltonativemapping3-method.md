---
title: ICorProfilerInfo9::GetILToNativeMapping3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetILToNativeMapping3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 46ceef43806fda9956797935c5eeec61f865dc6e
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973794"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a>Метод ICorProfilerInfo9:: GetILToNativeMapping3
  
 С учетом начального адреса машинного кода возвращает сведения о сопоставлении IL для этой откомпилированной версии кода.   
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```  
  
#### <a name="parameters"></a>Параметры  
 `pNativeCodeStartAddress` \
 окне Указатель на начало собственной функции.

 `cMap` \
 [in] Максимальный размер массива `map`. 

 `pcMap` \
 заполняет Общее число доступных структур COR_DEBUG_IL_TO_NATIVE_MAP.

 `map` \
 заполняет Массив структур [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) , каждый из которых задает смещения. После возврата метода `GetILToNativeMapping3` параметр `map` будет содержать все или некоторые из структур `COR_DEBUG_IL_TO_NATIVE_MAP`.

## <a name="remarks"></a>Примечания  
 Если включена многоуровневая компиляция, метод может иметь более одного тела машинного кода. [ICorProfilerInfo9:: жетнативекодестартаддрессес](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md) будет возвращать начальные адреса для всех частей машинного кода.

## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).  
  
 **Заголовок.** CorProf. idl, CorProf. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)] 
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)

