---
title: "Перечисление EClrFailure"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EClrFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: EClrFailure
helpviewer_keywords: EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e25a5378349dd476321765bb085db958e29670e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="eclrfailure-enumeration"></a>Перечисление EClrFailure
Описывает набор сбоев, для которых узел может задать действия политики.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|Произошла ошибка во время попытки выделения ресурсов (например, потока, блока памяти или блокировки) в некритической области кода.|  
|`FAIL_CriticalResource`|Произошла ошибка во время попытки выделения ресурсов (например, потока, блока памяти или блокировки) в критической области кода.|  
|`FAIL_FatalRuntime`|Общеязыковая среда выполнения (CLR) больше не может выполнять управляемый код в процессе. Исходя из этого вызовы любые размещения функции возвращают значение HRESULT значение HOST_E_CLRNOTAVAILABLE.|  
|`FAIL_OrphanedLock`|Поток не удалось снять блокировку возврата <xref:System.AppDomain> объекта. Узел нельзя установить не удалось вызвать прерывание потока.|  
|`FAIL_StackOverflow`|Произошло переполнение стека.|  
|`FAIL_AccessViolation`|Была предпринята попытка чтения или записи в защищенную область памяти. Не поддерживается в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].|  
|`FAIL_CodeContract`|Произошел сбой кода контракта. В разделе [контрактов кода](../../../../docs/framework/debug-trace-profile/code-contracts.md).|  
  
## <a name="remarks"></a>Примечания  
 В разделе [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) метод список [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значения узла можно использовать для указания действия политики условий ошибок. Дополнительные сведения о критических и некритических областях кода см. в разделе [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [Метод SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)  
 [Интерфейс IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
