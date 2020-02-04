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
ms.openlocfilehash: b860cf6eb07c3f063e3e51514f8492cf4af9e8ed
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869676"
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
  
## <a name="remarks"></a>Заметки  
  
> [!IMPORTANT]
> Этот метод устарел. Он Возвращает COR_E_OVERFLOW для объектов размером более 4 ГБ на 64-разрядных платформах. Используйте вместо этого метод [метод icorprofilerinfo4:: GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md) .  
  
 Различные объекты одних и тех же типов часто имеют одинаковый размер. Однако некоторые типы, такие как массивы или строки, могут иметь разные размеры для каждого объекта.  
  
 Размер, возвращаемый методом `GetObjectSize`, не включает заполнение выравнивания, которое может появиться после того, как объект находится в куче сборки мусора. Если для перехода от объекта к объекту в куче сборки мусора используется метод `GetObjectSize`, то при необходимости добавьте заполнение выравнивания вручную.  
  
- В 32-разрядных Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 и COR_PRF_GC_GEN_2 использовать 4-байтовый выравнивание, а COR_PRF_GC_LARGE_OBJECT_HEAP использует 8-байтное выравнивание.  
  
- В 64-разрядной Windows выравнивание всегда равно 8 байтам.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
