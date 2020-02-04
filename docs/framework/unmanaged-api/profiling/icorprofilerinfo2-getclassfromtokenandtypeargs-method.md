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
ms.openlocfilehash: e0663ff122397ba639a0a219e513be2f3f0cbbef
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862794"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>Метод ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
Возвращает `ClassID` типа, используя указанный токен метаданных и `ClassID` значения любых аргументов типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleID`  
 окне Идентификатор модуля, в котором находится тип.  
  
 `typeDef`  
 окне Токен метаданных `mdTypeDef`, ссылающийся на тип.  
  
 `cTypeArgs`  
 окне Число параметров типа для данного типа. Для типов, не являющихся универсальными, это значение должно быть равно нулю.  
  
 `typeArgs`  
 окне Массив значений `ClassID`, каждый из которых является аргументом типа. Значение `typeArgs` может быть равно NULL, если `cTypeArgs` имеет значение 0.  
  
 `pClassID`  
 заполняет Указатель на `ClassID` указанного типа.  
  
## <a name="remarks"></a>Заметки  
 Вызов метода `GetClassFromTokenAndTypeArgs` с `mdTypeRef`, а не `mdTypeDef` маркером метаданных, может иметь непредсказуемые результаты. вызывающие объекты должны разрешить `mdTypeRef` в `mdTypeDef` при передаче.  
  
 Если тип еще не загружен, вызов `GetClassFromTokenAndTypeArgs` запустит загрузку, что является опасной операцией во многих контекстах. Например, вызов этого метода во время загрузки модулей или других типов может привести к бесконечному циклу, так как среда выполнения пытается циклически загружать вещи.  
  
 В общем случае использование `GetClassFromTokenAndTypeArgs` не рекомендуется. Если профилировщики заинтересованы в событиях для определенного типа, они должны хранить `ModuleID` и `mdTypeDef` этого типа, а также использовать [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) для проверки того, является ли данный `ClassID` требуемым типом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
