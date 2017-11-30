---
title: "Метод ICorDebugProcess2::SetDesiredNGENCompilerFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 278f1f79fd929aa8a0c3233e68b30b1154e913ef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>Метод ICorDebugProcess2::SetDesiredNGENCompilerFlags
Задает флаги, которые должны быть внедрены в компилируемый образ для выполнения, чтобы загрузить этот образ в текущий процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pdwFlags`  
 [in] Значение [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) перечисление, указывающее флаги компилятора, используемый для выбора нужного предварительно скомпилированного образа.  
  
## <a name="remarks"></a>Примечания  
 `SetDesiredNGENCompilerFlags` Метод задает флаги, которые должны быть внедрены в компилируемый образ, чтобы среда выполнения будет загружать этот образ в этот процесс. Флаги, установленные с помощью данного метода используются только для выбора надлежащего предварительно скомпилированного образа. Если изображение не существует, среда выполнения будет загрузить изображение Microsoft промежуточного языка MSIL и компилятор just-in-time (JIT). В этом случае необходимо использовать отладчик [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) метод, чтобы задать флаги в случае необходимости для JIT-компиляции.  
  
 Если загружается образ, но определенную JIT-компиляцию для него (что произойдет в случае, если изображение содержит универсальные шаблоны), необходимо выполнить указанные флаги компилятора по `SetDesiredNGENCompilerFlags` метод будет применяться к дополнительной JIT-компиляции.  
  
 `SetDesiredNGENCompilerFlags` Метод должен вызываться во время [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) обратного вызова. Пытается вызвать `SetDesiredNGENCompilerFlags` метод впоследствии завершится с ошибкой. Кроме того, попытки задать флаги, которые либо не определены в `CorDebugJITCompilerFlags` перечисления являются не разрешен для данного процесса, произойдет сбой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICorDebug-интерфейс](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [ICorDebugManagedCallback-интерфейс](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
