---
title: "Перечисление EPolicyAction"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EPolicyAction
api_location: mscoree.dll
api_type: COM
f1_keywords: EPolicyAction
helpviewer_keywords: EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5de55d46eead37962fad7d7c1c5bd1766e772fe8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="epolicyaction-enumeration"></a>Перечисление EPolicyAction
Описывает действия политики, основное приложение может задать для операций, описанных [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) и сбоев, описанных [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`eAbortThread`|Указывает, общеязыковой среды выполнения (CLR) следует прервать надлежащим образом поток. Прерывание надлежащим образом предполагает попытки выполнить все `finally` блокирует любой `catch` , связанных с прерывания потока и методы завершения.|  
|`eDisableRuntime`|Указывает, что среда CLR должна перейти в отключенное состояние. Дальнейшая управляемый код может выполняться в соответствующий процесс и потоки блокируются попадающие в CLR.|  
|`eExitProcess`|Указывает, что среда CLR следует выполнять надлежащего выхода из процесса, включая выполнение методов завершения и очистки и ведение журнала операций.|  
|`eFastExitProcess`|Указывает, что среда CLR должна выхода из процесса немедленно, без выполнения методов завершения или очистки и ведение журнала операций. При этом отладчику отправляется уведомление отладчика.|  
|`eNoAction`|Указывает, что никакие действия не выполнены.|  
|`eRudeAbortThread`|Указывает, что среда CLR выполнение грубое прерывание потока. Только те `catch` и `finally` блоки, отмеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute> выполняются.|  
|`eRudeExitProcess`|Указывает, что среда CLR должна выхода из процесса без выполнения методов завершения или ведение журнала операций.|  
|`eRudeUnloadAppDomain`|Указывает выполнение с CLR грубые выгрузку <xref:System.AppDomain>. Методы завершения только отмеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute> выполняются. Аналогичным образом, все потоки с этим <xref:System.AppDomain> их стека получать `ThreadAbortException`, но только те, которые `catch` и `finally` блоки, отмеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute> выполняются.|  
|`eThrowException`|Указывает, что соответствующий условию, например о нехватке памяти, переполнение буфера и т. д. должны быть исключение.|  
|`eUnloadAppDomain`|Указывает, что <xref:System.AppDomain> должна быть выгружена. Среда CLR пытается запустить методы завершения.|  
  
## <a name="remarks"></a>Примечания  
 Основное приложение задает действия в рамках политики путем вызова методов [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) интерфейса. Сведения о принудительном и надлежащих см. в разделе [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) перечисления.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисление EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [Интерфейс IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
