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
ms.openlocfilehash: 299a7495d9ca9215ad21301a3ac525fa6e49a01b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130345"
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
 Метод возвращает `S_OK`, если длина потока памяти может быть определена, даже если она равна нулю (0).  
  
 Метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC`, если метод был создан с помощью <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="remarks"></a>Заметки  
 Если модуль содержит символы в памяти, длина потока помещается в `pCountSymbolBytes`. Если у модуля нет символов в памяти, `*pCountSymbolBytes = 0`.  
  
> [!NOTE]
> Текущая реализация не поддерживает отражение. Emit. Если модуль был создан с помощью отражения. Emit, метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
