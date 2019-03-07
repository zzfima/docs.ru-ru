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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 642c4fd600d10ef89a08aa32bef5c8e7455552c7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473834"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a>Метод ICorDebugModule::EnableJITDebugging
Определяет, сохраняет ли компилятор just-in-time (JIT) сведения об отладке для методов в данном модуле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `bTrackJITInfo`  
 [in] Это значение равно `true` для включения JIT-компилятор для сохранения сведений о сопоставлении между версией Microsoft промежуточного языка MSIL и версии JIT-компиляции каждого метода в данном модуле.  
  
 `bAllowJitOpts`  
 [in] Это значение равно `true` для включения JIT-компилятор для создания кода с помощью определенных реализаций определенных JIT-компилятора для отладки.  
  
## <a name="remarks"></a>Примечания  
 JIT-отладка включена по умолчанию для всех модулей, загруженных при активном отладчике. Программное Включение или отключение параметров переопределяет глобальные параметры.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
