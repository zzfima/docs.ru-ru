---
title: Метод ICorProfilerInfo::GetClassFromToken
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 841953625235406f013e9f140ad91c7b65680e47
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863957"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a>Метод ICorProfilerInfo::GetClassFromToken
Возвращает идентификатор класса по заданному маркеру метаданных. Этот метод является устаревшим в .NET Framework версии 2,0. Вместо этого используйте [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleID`  
 окне Идентификатор модуля, содержащего класс.  
  
 `typeDef`  
 окне Токен метаданных `mdTypeDef`, ссылающийся на класс.  
  
 `cTypeArgs`  
 заполняет Указатель на идентификатор класса.  
  
## <a name="remarks"></a>Заметки  
 Этот метод устарел; Вместо этого используйте `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` для всех типов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 1,0, 1,1  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
