---
title: "Метод ICorConfiguration::AddDebuggerSpecialThread"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.AddDebuggerSpecialThread
api_location: mscoree.dll
api_type: COM
f1_keywords: AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2501461267ff7369cd9c48f4cef6cda42063a48b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a>Метод ICorConfiguration::AddDebuggerSpecialThread
Указывает службы отладки, в определенном потоке, что следует разрешить продолжить выполнение при завершении работы приложения во время отладки сценариев управляемого или неуправляемого отладчика.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwSpecialThreadId`  
 [in] Идентификатор потока, должны продолжать выполнение.  
  
## <a name="remarks"></a>Примечания  
 Указанный поток не может выполнить управляемый код или вход в среду выполнения каким-либо образом. Примером такого потока может служить поток в процессе, для поддержки сценариев прежних версий отладчики.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Icorconfiguration-интерфейс](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
