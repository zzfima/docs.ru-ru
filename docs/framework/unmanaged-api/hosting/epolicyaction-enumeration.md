---
title: Перечисление EPolicyAction
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa8589b3f27ba97d32e77dbfecb190edc69dbc18
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57677335"
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
|`eAbortThread`|Указывает, что среда CLR (CLR) следует прервать поток корректно. Корректное прерывание включает пытается запустить все `finally` блокирует любой `catch` , связанных с прерывания потоков и методы завершения.|  
|`eDisableRuntime`|Указывает, что среда CLR следует перейти в отключенное состояние. Дальнейшая управляемый код может выполняться в соответствующий процесс, а потоки блокируются из входа в среду CLR.|  
|`eExitProcess`|Указывает, что среда CLR следует выполнять надлежащего выхода из процесса, включая выполнение методов завершения и очистки и операции ведения журнала.|  
|`eFastExitProcess`|Указывает, что среда CLR следует выйти из процесса немедленно, без выполнения методов завершения или очистки и операции ведения журнала. Тем не менее отладчик отправляется уведомление.|  
|`eNoAction`|Указывает, что следует принимать никаких действий.|  
|`eRudeAbortThread`|Указывает, что среда CLR выполнение грубое прерывание потока. Только те `catch` и `finally` блоки, отмеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute> выполняются.|  
|`eRudeExitProcess`|Указывает, что среда CLR следует выйти из процесса без выполнения методов завершения или ведение журнала операций.|  
|`eRudeUnloadAppDomain`|Указывает выполнение с CLR грубые выгрузки из <xref:System.AppDomain>. Только методы завершения, отмеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute> выполняются. Аналогичным образом, все потоки с этим <xref:System.AppDomain> в их stack получать `ThreadAbortException`, а только те `catch` и `finally` блоки, отмеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute> выполняются.|  
|`eThrowException`|Указывает, что должно вызываться исключение, соответствующие условию, например-памяти, переполнение буфера и т. д.|  
|`eUnloadAppDomain`|Указывает, что <xref:System.AppDomain> должна быть выгружена. Среда CLR пытается выполнять методы завершения.|  
  
## <a name="remarks"></a>Примечания  
 Основное приложение задает действия политики, вызывая методы класса [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) интерфейс. Сведения о ненадлежащих и надлежащих, см. в разделе [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) перечисления.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Перечисление EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [Интерфейс IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
