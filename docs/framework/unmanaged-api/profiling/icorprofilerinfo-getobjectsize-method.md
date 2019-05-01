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
ms.openlocfilehash: d366a0093ca82d2e5b3c40729777a1b6c0766bda
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049548"
---
# <a name="icorprofilerinfogetobjectsize-method"></a>Метод ICorProfilerInfo::GetObjectSize
Возвращает размер указанного объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a>Параметры  
 `objectId`  
 [in] Идентификатор объекта.  
  
 `pcSize`  
 [out] Указатель на размер объекта в байтах.  
  
## <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
>  Этот метод устарел. Он возвращает COR_E_OVERFLOW для объектов, размер которых превышает 4 ГБ на 64-разрядных платформах. Используйте [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) метод вместо этого.  
  
 Разные объекты одного типа часто имеют одинаковый размер. Тем не менее некоторые типы, например массивы или строки, возможно другого размера для каждого объекта.  
  
 Размер, возвращенный `GetObjectSize` метод не имеет любых заполнений выравнивания, которые могут появиться после объект находится в куче сбора мусора. Если вы используете `GetObjectSize` метод для перехода от объекта к объекту в куче сбора мусора, добавить выравнивание, заполнение вручную, при необходимости.  
  
- На 32-разрядной Windows COR_PRF_GC_GEN_0 COR_PRF_GC_GEN_1 и COR_PRF_GC_GEN_2 4-байтового выравнивания, а COR_PRF_GC_LARGE_OBJECT_HEAP использует 8-байтового выравнивания.  
  
- На 64-разрядной Windows выравнивание всегда равен 8 байтам.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
