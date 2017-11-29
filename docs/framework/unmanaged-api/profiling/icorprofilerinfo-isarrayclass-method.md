---
title: "Метод ICorProfilerInfo::IsArrayClass"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.IsArrayClass
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cd07541095158d17b80333b83015d6b1f33a5dcc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICorProfilerInfo-интерфейс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
