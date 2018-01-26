---
title: "Метод ICorProfilerInfo::GetObjectSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetObjectSize
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9425938042485c4330fe3fbc50cdabde6451b427
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetobjectsize-method"></a>Метод ICorProfilerInfo::GetObjectSize
Возвращает размер указанного объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
#### <a name="parameters"></a>Параметры  
 `objectId`  
 [in] Идентификатор объекта.  
  
 `pcSize`  
 [out] Указатель на размер объекта в байтах.  
  
## <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
>  Этот метод устарел. Он возвращает COR_E_OVERFLOW для объектов более 4 ГБ на 64-разрядных платформах. Используйте [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) метод вместо него.  
  
 Разные объекты одного типа часто имеют одинаковый размер. Однако некоторые типы, например массивов или строк, могут иметь другого размера для каждого объекта.  
  
 Размер, возвращаемый `GetObjectSize` метода не включает заполнения выравнивание, может появиться после объекта в куче сбора мусора. Если вы используете `GetObjectSize` метод перемещаться от объекта к объекту в куче сбора мусора, добавлять заполнение вручную, при необходимости выравнивания.  
  
-   На 32-разрядной версии Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 и COR_PRF_GC_GEN_2 используется 4-байтовое выравнивание, а COR_PRF_GC_LARGE_OBJECT_HEAP 8-байтового выравнивания.  
  
-   На 64-разрядной версии Windows выравнивание всегда равно 8 байт.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
