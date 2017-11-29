---
title: "Метод ICorProfilerInfo2::GetClassFromTokenAndTypeArgs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 332be5616ac11fc89df8c8d54aa5c0cbc49491ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>Метод ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
Возвращает `ClassID` типа, используя указанный токен метаданных и `ClassID` значения любого типа аргументов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
#### <a name="parameters"></a>Параметры  
 `moduleID`  
 [in] Идентификатор модуля, в котором находится тип.  
  
 `typeDef`  
 [in] `mdTypeDef` Токен метаданных, который ссылается на тип.  
  
 `cTypeArgs`  
 [in] Число параметров типа для заданного типа. Это значение должно быть нулем для неуниверсальных типов.  
  
 `typeArgs`  
 [in] Массив `ClassID` значений, каждое из которых является аргументом типа. Значение `typeArgs` может иметь значение NULL, если `cTypeArgs` присваивается нулевое значение.  
  
 `pClassID`  
 [out] Указатель на `ClassID` указанного типа.  
  
## <a name="remarks"></a>Примечания  
 Вызов `GetClassFromTokenAndTypeArgs` метод с `mdTypeRef` вместо `mdTypeDef` токен метаданных может привести к непредсказуемым результатам, вызывающие объекты должны устранить `mdTypeRef` для `mdTypeDef` во время передачи.  
  
 Если тип еще не загружено, вызов метода `GetClassFromTokenAndTypeArgs` активируют загрузки, которая является опасной операцией во множестве контекстов. Например вызов этого метода во время загрузки модулей или других типов может привести к бесконечному циклу, как среда выполнения пытается циклически загрузить объекты.  
  
 Как правило, использование `GetClassFromTokenAndTypeArgs` не рекомендуется. Если профилировщик интересуют события для конкретного типа, они сохраняют `ModuleID` и `mdTypeDef` указанного типа, используйте [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) для проверки ли данный `ClassID` , представляет требуемый тип.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICorProfilerInfo-интерфейс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-интерфейс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
