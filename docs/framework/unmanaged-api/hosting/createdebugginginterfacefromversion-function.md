---
title: Функция CreateDebuggingInterfaceFromVersion
ms.date: 03/30/2017
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 247383e267ab3e8932d43621e122986a59d9a30d
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490513"
---
# <a name="createdebugginginterfacefromversion-function"></a>Функция CreateDebuggingInterfaceFromVersion
Создает [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) объекта на основе указанной версии данных.  
  
 Эта функция является устаревшим в .NET Framework 4. Вместо этого, чтобы получить интерфейс для общеязыковой среды выполнения (CLR) 2.0, используйте [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) метод и укажите идентификатор класса CLSID_CLRDebuggingLegacy и IID_ICorDebug идентификатор интерфейса. Чтобы получить интерфейс для CLR 4 или более поздней версии, вызовите [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) функцию и укажите идентификатор класса CLSID_CLRDebugging и IID_ICLRDebugging идентификатор интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `iDebuggerVersion`  
 [in] Версия `ICorDebug` ведь отладчиком. См. в разделе [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) перечисления для допустимых значений.  
  
 `szDebuggeeVersion`  
 [in] Распространенные версию среды CLR, связанный с приложением или процесс для отладки. См. в разделе [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) или [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) сведения о получении этого значения.  
  
 `ppCordb`  
 [out] Получает указатель на расположение `ICorDebug` объекта.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, а также следующие значения.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|`szDebuggeeVersion` или `ppCordb` имеет значение null, или версии Неверная строка.|  
  
## <a name="remarks"></a>Примечания  
 `szDebuggeeVersion` Параметр сопоставляется с соответствующей версией библиотеки MSCorDbi.dll.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
