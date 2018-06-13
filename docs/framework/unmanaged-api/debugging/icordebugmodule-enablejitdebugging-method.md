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
ms.openlocfilehash: 71722293bfb80a7e57393916560f922d970ea2ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415646"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a>Метод ICorDebugModule::EnableJITDebugging
Определяет, сохраняет ли компилятор just-in-time (JIT), сведения об отладке для методов в этом модуле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `bTrackJITInfo`  
 [in] Это значение равно `true` для включения JIT-компилятором для сохранения сведений о сопоставлении между версией Microsoft промежуточного языка MSIL и версии JIT-компиляции каждого метода в данном модуле.  
  
 `bAllowJitOpts`  
 [in] Это значение равно `true` для включения JIT-компилятору создавать код с помощью определенные оптимизации конкретных JIT-компилятора для отладки.  
  
## <a name="remarks"></a>Примечания  
 JIT-отладка включена по умолчанию для всех модулей, загруженных при активном отладчик. Программное Включение или отключение параметров переопределяет глобальные настройки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
