---
title: Метод ICorProfilerInfo::GetILFunctionBody
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
ms.openlocfilehash: a7ec50c91ce02958d0d44643d4f79da1680532aa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450357"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>Метод ICorProfilerInfo::GetILFunctionBody
Возвращает указатель на тело метода в коде на языке MSIL, начиная с его заголовка.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleId`  
 окне Идентификатор модуля, в котором находится функция.  
  
 `methodId`  
 окне Токен метаданных для метода.  
  
 `ppMethodHeader`  
 заполняет Указатель на заголовок метода.  
  
 `pcbMethodSize`  
 заполняет Целое число, указывающее размер метода.  
  
## <a name="remarks"></a>Примечания  
 Метод ограничивается модулем, в котором он находится. Поскольку метод `GetILFunctionBody` предназначен для предоставления средству доступа к коду MSIL до того, как он будет загружен средой CLR, он использует маркер метаданных метода для поиска нужного экземпляра.  
  
 `GetILFunctionBody` может возвращать CORPROF_E_FUNCTION_NOT_IL HRESULT, если `methodId` указывает на метод без какого-либо кода MSIL (например, абстрактный метод или метод вызова платформы).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
