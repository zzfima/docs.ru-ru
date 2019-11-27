---
title: Метод ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
ms.openlocfilehash: 41021a524142afe34727584265aee578e31a64b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433211"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>Метод ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
Возвращает `FunctionID` функции с помощью указанного маркера метаданных, содержащего класс, и `ClassID` значений любых аргументов типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleID`  
 окне Идентификатор модуля, в котором находится функция.  
  
 `funcDef`  
 окне Токен метаданных `mdMethodDef`, ссылающийся на функцию.  
  
 `classId`  
 окне Идентификатор содержащего класса функции.  
  
 `cTypeArgs`  
 окне Число параметров типа для данной функции. Для неуниверсальных функций это значение должно быть равно нулю.  
  
 `typeArgs`  
 окне Массив значений `ClassID`, каждый из которых является аргументом функции. Значение `typeArgs` может быть равно NULL, если `cTypeArgs` имеет значение 0.  
  
 `pFunctionID`  
 заполняет Указатель на `FunctionID` указанной функции.  
  
## <a name="remarks"></a>Заметки  
 Вызов метода `GetFunctionFromTokenAndTypeArgs` с метаданными `mdMethodRef`, а не `mdMethodDef` маркером метаданных, может иметь непредсказуемые результаты. Вызывающие объекты должны разрешить `mdMethodRef` в `mdMethodDef` при передаче.  
  
 Если функция еще не загружена, вызов `GetFunctionFromTokenAndTypeArgs` приведет к возникновению загрузки, что является опасной операцией во многих контекстах. Например, вызов этого метода во время загрузки модулей или типов может привести к бесконечному циклу, так как среда выполнения пытается циклически загружать вещи.  
  
 В общем случае использование `GetFunctionFromTokenAndTypeArgs` не рекомендуется. Если профилировщики заинтересованы в событиях для определенной функции, они должны хранить `ModuleID` и `mdMethodDef` этой функции, а также использовать [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) для проверки того, является ли данный `FunctionID` требуемой функцией.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
