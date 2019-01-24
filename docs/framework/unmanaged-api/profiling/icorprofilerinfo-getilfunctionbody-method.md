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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9e1ef61271e5b413972b8ba40a8fe8bac60ceeb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566223"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>Метод ICorProfilerInfo::GetILFunctionBody
Получает указатель в теле метода в код MSIL (MSIL), начиная с его заголовка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a>Параметры  
 `moduleId`  
 [in] Идентификатор модуля, в которой находится функция.  
  
 `methodId`  
 [in] Токен метаданных для метода.  
  
 `ppMethodHeader`  
 [out] Указатель на заголовок метода.  
  
 `pcbMethodSize`  
 [out] Целое число, указывающее размер метода.  
  
## <a name="remarks"></a>Примечания  
 Метод ограничивается модуля, в котором он находится. Так как `GetILFunctionBody` метод предназначен для предоставления доступа для кода на языке MSIL, прежде чем он был загружен с общеязыковой среды выполнения (CLR), для поиска требуемого экземпляра используется токен метаданных метода.  
  
 `GetILFunctionBody` может возвращать CORPROF_E_FUNCTION_NOT_IL HRESULT, если `methodId` указывает на метод без любой MSIL кода (например, абстрактный метод или платформа вызова метода (PInvoke)).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
