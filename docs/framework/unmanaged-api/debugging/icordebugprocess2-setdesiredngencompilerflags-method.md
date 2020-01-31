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
ms.openlocfilehash: 9f62d94d30c8c4f23073895b8ff0f7afa2dbad6b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792488"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>Метод ICorDebugProcess2::SetDesiredNGENCompilerFlags
Задает флаги, которые должны быть внедрены в предкомпилированное изображение, чтобы среда выполнения загружала этот образ в текущий процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pdwFlags`  
 окне Значение перечисления [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) , указывающее флаги компилятора, используемые для выбора правильного предварительно скомпилированного изображения.  
  
## <a name="remarks"></a>Заметки  
 Метод `SetDesiredNGENCompilerFlags` задает флаги, которые должны быть внедрены в предкомпилированное изображение, чтобы среда выполнения загружала этот образ в этот процесс. Флаги, заданные этим методом, используются только для выбора правильного предкомпилированного изображения. Если такого образа не существует, среда выполнения загрузит образ MSIL и JIT-компилятор, вместо этого. В этом случае отладчик должен по-прежнему использовать метод [ICorDebugModule2:: SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) , чтобы установить флаги для JIT-компиляции.  
  
 Если изображение загружено, но для этого образа необходимо выполнить некоторые JIT-компиляции (что будет так, если изображение содержит универсальные шаблоны), то флаги компилятора, заданные в методе `SetDesiredNGENCompilerFlags`, будут применяться к дополнительной JIT-компиляции.  
  
 Метод `SetDesiredNGENCompilerFlags` должен вызываться во время обратного вызова [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) . Попытка вызвать метод `SetDesiredNGENCompilerFlags` впоследствии завершится ошибкой. Кроме того, попытки установить флаги, которые либо не определены в перечислении `CorDebugJITCompilerFlags`, либо не являются допустимыми для данного процесса, завершатся ошибкой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebug](icordebug-interface.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
