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
ms.openlocfilehash: 96968956b513e1ae80a25f5fb4afea48bf888876
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739267"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a>Функция CreateDebuggingInterfaceFromVersion Silverlight
Принимает общую строку версии среды выполнения (CLR) языка, возвращенный [функция CreateVersionStringFromModule](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)и возвращает соответствующий интерфейс отладчика (как правило, [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szDebuggeeVersion`  
 [in] Строка версии среды CLR в целевом отлаживаемом объекте, который возвращается методом [функция CreateVersionStringFromModule](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md).  
  
 `ppCordb`  
 [out] Указатель на COM-объект (`IUnknown`). Этот объект будет привести к [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) объекта перед возвратом.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 `ppCordb` ссылается на допустимый объект, реализующий [интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) интерфейс.  
  
 E_INVALIDARG  
 Либо `szDebuggeeVersion`, либо `ppCordb` имеет значение null.  
  
 CORDBG_E_DEBUG_COMPONENT_MISSING  
 Не удалось найти компонент, который необходим для отладки среды CLR. Это означает, что не удалось найти mscordbi.dll или mscordaccore.dll в каталоге, где находится целевой объект CoreCLR.dll.  
  
 CORDBG_E_INCOMPATIBLE_PROTOCOL  
 Версия mscordbi.dll или mscordaccore.dll не совпадает с версией целевого объекта CoreCLR.dll.  
  
 E_FAIL (или другие коды возврата E_)  
 Не удалось вернуть [интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md).  
  
## <a name="remarks"></a>Примечания  
 Возвращаемый интерфейс предоставляет средства для подключения к среде CLR в целевом процессе и отладки управляемого кода, который выполняется в этой среде CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** dbgshim.h  
  
 **Библиотека:** dbgshim.dll  
  
 **Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)
