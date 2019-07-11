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
ms.openlocfilehash: 5e00e7f39bc2f8c14db0676102a52089c7710bd6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772264"
---
# <a name="icorprofilerinfoisarrayclass-method"></a>Метод ICorProfilerInfo::IsArrayClass
Определяет, является ли указанный класс класса массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a>Параметры  
 `classId`  
 [in] Идентификатор класса, который необходимо проверить.  
  
 `pBaseElemType`  
 [out] Указатель на значение CorElementType перечисления, указывающее тип элементов массива.  
  
 `pBaseClassId`  
 [out] Указатель на идентификатор класса для элементов массива, если они доступны.  
  
 `pcRank`  
 [out] Указатель на целое число, указывающее ранг (то есть число измерений) массива.  
  
## <a name="remarks"></a>Примечания  
 Если класс является классом массива, `IsArrayClass` метод возвращает значение S_OK HRESULT и значения для всех ненулевых выходных параметров. В противном случае возвращается значение S_FALSE.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
