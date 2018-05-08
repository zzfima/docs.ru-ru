---
title: Метод ICorProfilerModuleEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Skip method [.NET Framework profiling]
ms.assetid: 8dc29c6a-e2ba-41d8-a1e0-0fdd21421e0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 35256a25ed793ffee6ddc1b26088e0988fea5af2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilermoduleenumskip-method"></a>Метод ICorProfilerModuleEnum::Skip
Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
#### <a name="parameters"></a>Параметры  
 `celt`  
 [in] Число элементов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`celt` элементы были пропущены.|  
|S_FALSE|Менее `celt` элементы были пропущены, указывающая, что отсутствуют дополнительные элементы.|  
  
## <a name="remarks"></a>Примечания  
 Новое положение курсора данного перечислителя — (текущая позиция) + `celt`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
