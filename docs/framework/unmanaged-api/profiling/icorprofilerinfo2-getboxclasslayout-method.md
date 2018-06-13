---
title: Метод ICorProfilerInfo2::GetBoxClassLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f046fb51753bfa79d333d465e8850794ecc73973
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453542"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a>Метод ICorProfilerInfo2::GetBoxClassLayout
Получает сведения о расположении заданного типа значения при его упаковке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
#### <a name="parameters"></a>Параметры  
 `classId`  
 [in] Идентификатор класса, который описывает тип значения, который упаковывается.  
  
 `pBufferOffset`  
 [out] Целое число, — это смещение относительно указатель идентификатор упакованный объект типа значения.  
  
## <a name="remarks"></a>Примечания  
 `pBufferOffset` Значение представляет собой местоположение типа значения в поле. После `pBufferOffset` применяется для упакованного объекта макет класса тип значения можно использовать для интерпретации значения объекта.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
