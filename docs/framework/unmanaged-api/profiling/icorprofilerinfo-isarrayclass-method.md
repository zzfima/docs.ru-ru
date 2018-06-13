---
title: Метод ICorProfilerInfo::IsArrayClass
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f34fee19c796f65d315fcbd26d55e1d5322303a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453032"
---
# <a name="icorprofilerinfoisarrayclass-method"></a>Метод ICorProfilerInfo::IsArrayClass
Определяет, является ли указанный класс классом массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
#### <a name="parameters"></a>Параметры  
 `classId`  
 [in] Идентификатор класса необходимо проанализировать.  
  
 `pBaseElemType`  
 [out] Указатель на значение CorElementType перечисление, указывающее тип элементов массива.  
  
 `pBaseClassId`  
 [out] Указатель на идентификатор класса элементов массива, если оно доступно.  
  
 `pcRank`  
 [out] Указатель на целое число, указывающее ранг (то есть число измерений) массива.  
  
## <a name="remarks"></a>Примечания  
 Если класс является классом массивов `IsArrayClass` метод возвращает значение S_OK HRESULT и значения для всех параметров, отличных от null выходные данные. В противном случае возвращает значение S_FALSE.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
