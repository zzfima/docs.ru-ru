---
title: Метод ICorDebugModule::EnableJITDebugging
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableJITDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type:
- apiref
ms.openlocfilehash: da532ee1b5909a68bedbb9e6f6c96333e88002a8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109726"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a>Метод ICorDebugModule::EnableJITDebugging
Определяет, сохраняет ли JIT-компилятор сведения об отладке для методов в этом модуле.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `bTrackJITInfo`  
 окне Присвойте этому параметру значение `true`, чтобы разрешить JIT-компилятору сохранять сведения о сопоставлении между версией MSIL и версией каждого метода в этом модуле, скомпилированном по требованию.  
  
 `bAllowJitOpts`  
 окне Задайте для этого параметра значение `true`, чтобы JIT-компилятор создавал код с определенными оптимизацией JIT для отладки.  
  
## <a name="remarks"></a>Заметки  
 JIT-отладка включается по умолчанию для всех модулей, загружаемых при активном отладчике. Программное включение или отключение параметров переопределяет глобальные параметры.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
