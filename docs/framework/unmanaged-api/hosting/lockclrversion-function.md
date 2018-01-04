---
title: "Функция LockClrVersion"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: LockClrVersion
helpviewer_keywords: LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a58d7e99f545026f6f133901ef35a1f9b9fabc7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="lockclrversion-function"></a>Функция LockClrVersion
Предоставляет узлу возможность определить, какая версия среды common language runtime (CLR), которая будет использоваться в процессе до явной инициализации среды CLR.  
  
 Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
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
 [in] Функция, вызываемая при инициализации среды CLR.  
  
 `pBeginHostSetup`  
 [in] Функция, вызываемая узлом сообщать среде CLR, инициализация выполняется запуск.  
  
 `pEndHostSetup`  
 [in] Функция, вызываемая узлом сообщать среде CLR, инициализация завершена.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, кроме следующих значений.  
  
|Код возврата|Описание:|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|Один или несколько аргументов имеет значение null.|  
  
## <a name="remarks"></a>Примечания  
 Узел вызывает метод `LockClrVersion` перед инициализацией среды CLR. `LockClrVersion`принимает три параметра, все из которых являются обратными вызовами типа [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md). Этот тип определяется следующим образом.  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 При инициализации среды выполнения, выполняются следующие действия:  
  
1.  Узел вызывает метод [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или одну из функций инициализации среды выполнения. Кроме того узел может инициализировать среду выполнения, с помощью активации COM-объекта.  
  
2.  Среда выполнения вызывает функции, указанной `hostCallback` параметра.  
  
3.  Функции, указанной `hostCallback` затем вызывает следующую последовательность вызовов:  
  
    -   Функции, указанной `pBeginHostSetup` параметра.  
  
    -   `CorBindToRuntimeEx`(или другую функцию инициализации среды выполнения).  
  
    -   [ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).  
  
    -   [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).  
  
    -   Функции, указанной `pEndHostSetup` параметра.  
  
 Все вызовы из `pBeginHostSetup` для `pEndHostSetup` должно находиться на одном потоке или нити с использованием одного логического стека. Этот поток может отличаться от потока, на котором `hostCallback` вызывается.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
