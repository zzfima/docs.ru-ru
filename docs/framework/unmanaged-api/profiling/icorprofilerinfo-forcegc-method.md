---
title: Метод ICorProfilerInfo::ForceGC
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 06601b1aa675dd9ecf023a9f83d881ba1591ac52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfoforcegc-method"></a>Метод ICorProfilerInfo::ForceGC
Принудительно начинает сборку мусора в общеязыковой среде выполнения (CLR).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a>Примечания  
 `ForceGC` Метод должен вызываться только из потока, который имеет не выполнял управляемый код и не имеет обратные вызовы профилировщика его стека. Наиболее удобным реализация заключается в создании отдельного потока в профилировщике, который вызывает `ForceGC` при получении сигнала.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
