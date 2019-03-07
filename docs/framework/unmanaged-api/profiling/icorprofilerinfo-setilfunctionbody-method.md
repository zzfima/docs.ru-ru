---
title: Метод ICorProfilerInfo::SetILFunctionBody
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8c640e565374adfdc2a409036910f1a7e0f6f8ba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472269"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a>Метод ICorProfilerInfo::SetILFunctionBody
Заменяет текст в указанном модуле указанной функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleId`  
 [in] Идентификатор модуля, в которой находится функция.  
  
 `methodid`  
 [in] Токен функции, для которой заменяемый текст.  
  
 `pbNewILMethodHeader`  
 [in] Новый заголовок для функции.  
  
## <a name="remarks"></a>Примечания  
 `SetILFunctionBody` Метод заменяет относительный виртуальный адрес функции в метаданных, так что он указывает на новый тело функции и настраивает все внутренние структуры данных при необходимости.  
  
 `SetILFunctionBody` Метод может вызываться для только для тех функций, которые никогда не были скомпилированы с помощью компилятора just-in-time (JIT).  
  
 Используйте [ICorProfilerInfo::GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) метод, чтобы выделить место для нового метода обеспечить совместимость буфера.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
