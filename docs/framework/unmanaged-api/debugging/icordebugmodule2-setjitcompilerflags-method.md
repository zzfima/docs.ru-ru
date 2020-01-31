---
title: Метод ICorDebugModule2::SetJITCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
ms.openlocfilehash: b28e457ea0b51d320581c0fbe36574698081ea36
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792965"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>Метод ICorDebugModule2::SetJITCompilerFlags
Задает флаги, управляющие JIT-компиляцией этого ICorDebugModule2.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwFlags`  
 окне Побитовое сочетание значений перечисления [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) .  
  
## <a name="remarks"></a>Заметки  
 Если `dwFlags` значение недопустимо, метод `SetJITCompilerFlags` завершится ошибкой.  
  
 Метод `SetJITCompilerFlags` можно вызвать только в обратном вызове [ICorDebugManagedCallback:: LoadModule](icordebugmanagedcallback-loadmodule-method.md) для этого модуля. Попытки вызвать его после доставки `ICorDebugManagedCallback::LoadModule`ного обратного вызова завершатся ошибкой.  
  
 "Изменить и продолжить" не поддерживается на платформах 64-разрядных или Win9x. Поэтому при вызове метода `SetJITCompilerFlags` на любой из этих двух платформ с флагом CORDEBUG_JIT_ENABLE_ENC, установленным в `dwFlags`, метод `SetJITCompilerFlags` и все методы, относящиеся к Edit и Continue, такие как [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md), завершатся ошибкой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
