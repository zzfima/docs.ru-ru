---
title: Функция CreateDebuggingInterfaceFromVersion Silverlight
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53571268391011cc1dc0ff112d484e1fa140057f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a>Функция CreateDebuggingInterfaceFromVersion Silverlight
Принимает общую строку языка версии среды CLR, возвращенный [функция CreateVersionStringFromModule](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)и возвращает соответствующий интерфейс отладчика (как правило, [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `szDebuggeeVersion`  
 [in] Строка версии среды CLR в целевом отлаживаемом объекте, который возвращается методом [функция CreateVersionStringFromModule](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md).  
  
 `ppCordb`  
 [out] Указатель на COM-объект (`IUnknown`). Этот объект будет приведен к [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) объекта перед его возвращением.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 `ppCordb` ссылается на допустимый объект, реализующий [интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) интерфейса.  
  
 E_INVALIDARG  
 Либо `szDebuggeeVersion`, либо `ppCordb` имеет значение null.  
  
 CORDBG_E_DEBUG_COMPONENT_MISSING  
 Не удалось найти компонент, который необходим для отладки среды CLR. Это означает, что не удалось найти mscordbi.dll или mscordaccore.dll в каталоге, где находится целевой объект CoreCLR.dll.  
  
 CORDBG_E_INCOMPATIBLE_PROTOCOL  
 Версия mscordbi.dll или mscordaccore.dll не совпадает с версией целевого объекта CoreCLR.dll.  
  
 E_FAIL (или другие коды возврата E_)  
 Невозможно вернуть [интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md).  
  
## <a name="remarks"></a>Примечания  
 Возвращаемый интерфейс предоставляет средства для подключения к среде CLR в целевом процессе и отладки управляемого кода, который выполняется в этой среде CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** dbgshim.h  
  
 **Библиотека:** dbgshim.dll  
  
 **Версии платформы .NET framework:** 3.5 SP1
