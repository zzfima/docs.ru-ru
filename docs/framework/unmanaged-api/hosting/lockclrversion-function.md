---
title: Функция LockClrVersion
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95f61170d401161dcf217f139dbe6e4c6d3a0e0c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735043"
---
# <a name="lockclrversion-function"></a>Функция LockClrVersion
Позволяет основному приложению определить, какую версию общеязыковой среды выполнения (CLR), которая будет использоваться в процессе до явной инициализации среды CLR.  
  
 Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `hostCallback`  
 [in] Функция, которая вызывается средой CLR при инициализации.  
  
 `pBeginHostSetup`  
 [in] Функция, которая вызывается узлом для сообщать среде CLR, инициализация выполняется запуск.  
  
 `pEndHostSetup`  
 [in] Функция, которая вызывается узлом для сообщать среде CLR, инициализация завершена.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, помимо следующих значений.  
  
|Код возврата|Описание:|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|Один или несколько аргументов имеет значение null.|  
  
## <a name="remarks"></a>Примечания  
 Узел вызывает метод `LockClrVersion` перед инициализацией среды CLR. `LockClrVersion` принимает три параметра, все из которых являются обратные вызовы типа [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md). Этот тип определяется следующим образом.  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 При инициализации среды выполнения, выполняются следующие действия:  
  
1.  Узел вызывает метод [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или одну из функций инициализации среды выполнения. Кроме того узел может инициализировать среду выполнения, с помощью активации COM-объекта.  
  
2.  Среда выполнения вызывает функцию, указанную аргументом `hostCallback` параметра.  
  
3.  Функцию, указанную аргументом `hostCallback` затем выполняет следующую последовательность вызовов:  
  
    -   Функцию, указанную аргументом `pBeginHostSetup` параметра.  
  
    -   `CorBindToRuntimeEx` (или другую функцию инициализации среды выполнения).  
  
    -   [ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).  
  
    -   [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).  
  
    -   Функцию, указанную аргументом `pEndHostSetup` параметра.  
  
 Все вызовы из `pBeginHostSetup` для `pEndHostSetup` должно находиться на одном потоке или нити с использованием одного логического стека. Этот поток может отличаться от потока, на котором `hostCallback` вызывается.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
