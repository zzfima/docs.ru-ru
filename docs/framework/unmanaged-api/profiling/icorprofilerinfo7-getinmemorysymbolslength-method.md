---
title: 'Метод ICorProfilerInfo7:: GetInMemorySymbolsLength'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 157b0e215f8afa58cccb3d54a65baa9c307ba966
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955423"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>Метод ICorProfilerInfo7:: GetInMemorySymbolsLength
[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]  
  
 Возвращает длину потока символов в памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleId`  
 окне Идентификатор модуля, содержащего поток в памяти.  
  
 пкаунтсимболбитес  
 заполняет Указатель на `DWORD` значение, которое при возврате метода содержит длину потока в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Метод возвращает `S_OK` значение, если длина потока памяти может быть определена, даже если она равна нулю (0).  
  
 Метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC` значение, если метод был создан с <xref:System.Reflection.Emit?displayProperty=nameWithType>помощью.  
  
## <a name="remarks"></a>Примечания  
 Если модуль содержит символы в памяти, длина потока помещается в `pCountSymbolBytes`. Если у модуля нет символов в памяти, `*pCountSymbolBytes = 0`то.  
  
> [!NOTE]
> Текущая реализация не поддерживает отражение. Emit. Если модуль был создан с помощью отражения. Emit, метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC`значение.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf. idl, CorProf. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
