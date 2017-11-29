---
title: "Метод ICorDebugDataTarget::GetThreadContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.GetThreadContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 543956bb42d7477456426d7327f14b059b23d759
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a>Метод ICorDebugDataTarget::GetThreadContext
Возвращает текущий контекст потока для указанного потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwThreadID`  
 [in] Идентификатор потока, контекст которого требуется получить. Идентификатор определяется операционной системой.  
  
 `contextFlags`  
 [in] Побитовое сочетание флагов зависят от платформы, которые указывают, какие части контекста следует прочесть.  
  
 `contextSize`  
 [входной] Размер `pContext`.  
  
 `pContext`  
 [out] Буфер, в которой будет храниться контекст потока.  
  
## <a name="remarks"></a>Примечания  
 На платформах Windows `pContext` должно быть `CONTEXT` структуры (определенный в заголовке WinNT.h), соответствующий тип компьютера, указанный в [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) метод. `contextFlags`должен иметь те же значения, что `ContextFlags` поле `CONTEXT` структуры. `CONTEXT` Структуры зависит от процессора; Дополнительные сведения о файле WinNT.h.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICorDebugDataTarget-интерфейс](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
