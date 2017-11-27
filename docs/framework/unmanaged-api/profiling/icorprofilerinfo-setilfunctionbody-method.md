---
title: "Метод ICorProfilerInfo::SetILFunctionBody"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6d97827555ecefb775323fdf9dbd6577f941f1e9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a>Метод ICorProfilerInfo::SetILFunctionBody
Заменяет тело указанной функции в указанном модуле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a>Параметры  
 `moduleId`  
 [in] Идентификатор модуля, в которой находится функция.  
  
 `methodid`  
 [in] Токен функции, для которой необходимо заменить текст.  
  
 `pbNewILMethodHeader`  
 [in] Новый заголовок для функции.  
  
## <a name="remarks"></a>Примечания  
 `SetILFunctionBody` Метод заменяет относительный виртуальный адрес функции в метаданных, чтобы он указывает для нового тела функции и настраивает все внутренние структуры данных при необходимости.  
  
 `SetILFunctionBody` Метод может быть вызван на только те функции, которые никогда не были скомпилированы с помощью время JIT-компилятора.  
  
 Используйте [ICorProfilerInfo::GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) метод, чтобы выделить место для нового метода обеспечить совместимость буфера.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICorProfilerInfo-интерфейс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
