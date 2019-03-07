---
title: Метод ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ece4041f7fe4f9080db32a7edc2271b7f3beb95
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498943"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>Метод ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
Получает `ClassID` типа, используя указанный токен метаданных и `ClassID` значения любого типа аргументов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleID`  
 [in] Идентификатор модуля, в котором находится тип.  
  
 `typeDef`  
 [in] `mdTypeDef` Токен метаданных, который ссылается на тип.  
  
 `cTypeArgs`  
 [in] Число параметров типа для заданного типа. Это значение должно быть ноль для неуниверсальных типов.  
  
 `typeArgs`  
 [in] Массив `ClassID` значений, каждое из которых является аргументом типа. Значение `typeArgs` может иметь значение NULL, если `cTypeArgs` присваивается нулевое значение.  
  
 `pClassID`  
 [out] Указатель на `ClassID` указанного типа.  
  
## <a name="remarks"></a>Примечания  
 Вызов `GetClassFromTokenAndTypeArgs` метод с `mdTypeRef` вместо `mdTypeDef` токен метаданных может привести к непредсказуемым результатам; нужно будет разрешить вызывающим объектам `mdTypeRef` для `mdTypeDef` при передаче.  
  
 Если тип еще не загружено, вызов метода `GetClassFromTokenAndTypeArgs` активируют загрузки, которая является опасной операцией во многих контекстах. Например вызов этого метода во время загрузки модулей или других типов может привести к бесконечный цикл, как среда выполнения пытается циклически загружать объекты.  
  
 Как правило, использование `GetClassFromTokenAndTypeArgs` не рекомендуется. Если профилировщик интересуют события для определенного типа, их следует хранить `ModuleID` и `mdTypeDef` указанного типа, используйте [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) проверяемый ли заданный `ClassID` , — это требуемый тип.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
