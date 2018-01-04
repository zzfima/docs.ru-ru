---
title: "Метод ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b225b87eab6e65055618c8b6659459637e8a01be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>Метод ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
Возвращает `FunctionID` функции, используя указанный токен метаданных, содержащий класс, и `ClassID` значения любого типа аргументов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
#### <a name="parameters"></a>Параметры  
 `moduleID`  
 [in] Идентификатор модуля, в которой находится функция.  
  
 `funcDef`  
 [in] `mdMethodDef` Токен метаданных, который ссылается на функцию.  
  
 `classId`  
 [in] Идентификатор содержащего класса функции.  
  
 `cTypeArgs`  
 [in] Число параметров типа для данной функции. Это значение должно быть ноль для функций, не являющимися универсальными.  
  
 `typeArgs`  
 [in] Массив `ClassID` значений, каждое из которых является аргументом функции. Значение `typeArgs` может иметь значение NULL, если `cTypeArgs` присваивается нулевое значение.  
  
 `pFunctionID`  
 [out] Указатель на `FunctionID` указанной функции.  
  
## <a name="remarks"></a>Примечания  
 Вызов `GetFunctionFromTokenAndTypeArgs` метод с `mdMethodRef` метаданные вместо `mdMethodDef` токен метаданных может привести к непредсказуемым результатам. Вызывающие объекты должны устранить `mdMethodRef` для `mdMethodDef` во время передачи.  
  
 Если функция еще не загружено, вызов метода `GetFunctionFromTokenAndTypeArgs` приведет к загрузке могла выполняться, который является опасной операцией во множестве контекстов. Например вызов этого метода во время загрузки модулей или типов может привести к бесконечному циклу, как среда выполнения пытается циклически загрузить объекты.  
  
 Как правило, использование `GetFunctionFromTokenAndTypeArgs` не рекомендуется. Если профилировщик интересуют события для определенной функции, их следует хранить `ModuleID` и `mdMethodDef` этой функции, а также использовать [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) для проверки ли данный `FunctionID` — с нужной функции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
