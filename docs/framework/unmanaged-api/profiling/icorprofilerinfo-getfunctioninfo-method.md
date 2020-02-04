---
title: Метод ICorProfilerInfo::GetFunctionInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionInfo
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionInfo method [.NET Framework profiling]
- GetFunctionInfo method [.NET Framework profiling]
ms.assetid: c42b5891-019d-46b3-b551-4606295b75b8
topic_type:
- apiref
ms.openlocfilehash: 823cc5638ff3e0955aca0bd9ba5795f6b369c6b0
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863625"
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a>Метод ICorProfilerInfo::GetFunctionInfo
Возвращает родительский класс и токен метаданных для указанной функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 окне Идентификатор функции, для которой необходимо получить родительский класс и маркер метаданных.  
  
 `pClassId`  
 [выходной] Указатель на родительский класс функции.  
  
 `pModuleId`  
 [выходной] Указатель на модуль, в котором определен родительский класс функции.  
  
 `pToken`  
 [выходной] Указатель на токен метаданных функции.  
  
## <a name="remarks"></a>Заметки  
 Чтобы получить интерфейс метаданных для заданного модуля, код профилировщика может вызвать метод [ICorProfilerInfo:: жетмодулеметадата](icorprofilerinfo-getmodulemetadata-method.md) . Токен метаданных, возвращенный в расположение, на которое ссылается `pToken`, можно впоследствии использовать для доступа к метаданным функции.  
  
 `ClassID` функции в универсальном классе может быть невозможно получить без более контекстной информации об использовании функции. В этом случае `pClassId` будет иметь значение 0. Для предоставления большего контекста в коде профилировщика следует использовать [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) со значением COR_PRF_FRAME_INFO.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
