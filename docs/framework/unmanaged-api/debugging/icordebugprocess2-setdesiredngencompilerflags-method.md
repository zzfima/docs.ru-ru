---
title: Метод ICorDebugProcess2::SetDesiredNGENCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3582ebf2acee02d49aabafb03604c84249c4ce13
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747371"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>Метод ICorDebugProcess2::SetDesiredNGENCompilerFlags
Задает флаги, которые должны быть внедрены в компилируемый образ загрузки в текущий процесс в среде выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pdwFlags`  
 [in] Значение [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) перечисление, указывающее флаги компилятора, используемый для выбора нужного предварительно скомпилированного образа.  
  
## <a name="remarks"></a>Примечания  
 `SetDesiredNGENCompilerFlags` Метод задает флаги, которые должны быть внедрены в предварительно скомпилированный образ, чтобы среда выполнения будет загружать этот образ в этот процесс. Флаги, установленные с помощью данного метода используются только для выбора нужного предварительно скомпилированного образа. Если изображение отсутствует, среда выполнения загрузит образ Microsoft промежуточного языка MSIL и компилятор just-in-time (JIT) вместо этого. В этом случае отладчик по-прежнему необходимо использовать [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) метод, чтобы задать флаги для JIT-компиляцию полей.  
  
 Если загрузить образ, но определенную JIT-компиляцию необходимо выполнить для него (который будет в случае, если изображение содержит универсальные шаблоны), определяемое флаги компилятора `SetDesiredNGENCompilerFlags` метода будут применяться к дополнительной JIT-компиляции.  
  
 `SetDesiredNGENCompilerFlags` Метод должен вызываться во время [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) обратного вызова. Пытается вызвать `SetDesiredNGENCompilerFlags` метод впоследствии завершится с ошибкой. Кроме того, попытки задать флаги, которые либо не определены в `CorDebugJITCompilerFlags` перечисления являются недопустим для указанного процесса, произойдет сбой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
