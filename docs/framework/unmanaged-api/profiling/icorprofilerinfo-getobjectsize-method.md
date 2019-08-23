---
title: Метод ICorProfilerInfo::GetObjectSize
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetObjectSize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ad2092c902b137df0dfe108743ef4081ca5f04d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948116"
---
# <a name="icorprofilerinfogetobjectsize-method"></a>Метод ICorProfilerInfo::GetObjectSize
Возвращает размер указанного объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a>Параметры  
 `objectId`  
 окне Идентификатор объекта.  
  
 `pcSize`  
 заполняет Указатель на размер объекта в байтах.  
  
## <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
> Этот метод устарел. Он Возвращает COR_E_OVERFLOW для объектов, превышающих 4 ГБ на 64-разрядных платформах. Используйте вместо этого метод [метод icorprofilerinfo4:: GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) .  
  
 Различные объекты одних и тех же типов часто имеют одинаковый размер. Однако некоторые типы, такие как массивы или строки, могут иметь разные размеры для каждого объекта.  
  
 Размер, возвращаемый `GetObjectSize` методом, не включает заполнение выравнивания, которое может появиться после того, как объект находится в куче сборки мусора. При использовании `GetObjectSize` метода для перехода от объекта к объекту в куче сборки мусора при необходимости добавьте заполнение выравнивания вручную.  
  
- В 32-разрядных Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 и COR_PRF_GC_GEN_2 используют 4-байтное выравнивание, а COR_PRF_GC_LARGE_OBJECT_HEAP использует 8-байтное выравнивание.  
  
- В 64-разрядной Windows выравнивание всегда равно 8 байтам.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf. idl, CorProf. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
