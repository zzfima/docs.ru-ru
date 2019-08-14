---
title: 'ICorProfilerInfo10:: Жетлохобжектсизесрешолд'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.GetLOHObjectSizeThreshold
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: d6b6575cf04635b40b504b11bc415f61f05b4205
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974024"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a>Метод ICorProfilerInfo10:: Жетлохобжектсизесрешолд
  
 Возвращает значение заданного порога кучи больших объектов (LOH).   
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```  
  
#### <a name="parameters"></a>Параметры  
 `pThreshold` \
 заполняет Пороговое значение кучи больших объектов в байтах.
  
## <a name="remarks"></a>Примечания  
 Объекты, превышающие пороговое значение кучи больших объектов, будут выделены в куче больших объектов. Начиная с .NET Core 3,0, порог кучи больших объектов можно настроить, `pThreshold` он будет содержать пороговое значение активной кучи больших объектов в байтах.

## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).  
  
 **Заголовок.** CorProf. idl, CorProf. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerInfo10](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

