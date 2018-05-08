---
title: Функция CreateCordbObject
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12898f75d2575e539b018ea367bc870a3dc738a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="createcordbobject-function"></a>Функция CreateCordbObject
Создает интерфейс отладчика ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)), обеспечивающий функциональность для создания управляемого сеанса отладки в удаленном процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `iDebuggerVersion`  
 [in] Версия отладчика целевого процесса. Для удаленной отладки этот параметр должен иметь значение CorDebugVersion_2_0.  
  
 `ppCordb`  
 [out] Указатель на указатель на объект, который будет приведен к [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) и возвращаться.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Количество сред CLR в процессе успешно определено, и соответствующие массивы дескрипторов и путей заполнены должным образом.  
  
 E_INVALIDARG  
 Параметр `ppCordb` имеет значение null, или параметр `iDebuggerVersion` не имеет значение CorDebugVersion_2_0.  
  
 E_OUTOFMEMORY  
 Не удается выделить достаточно памяти для `ppCordb`.  
  
 E_FAIL (или другие коды возврата E_)  
 Прочие сбои.  
  
## <a name="remarks"></a>Примечания  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) интерфейс, который возвращается в `ppCordb` является интерфейсом верхнего уровня отладки для всех управляемых служб отладки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Библиотека:** mscordbi_macx86.dll  
  
 **Версии платформы .NET framework:** 3.5 SP1
