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
ms.openlocfilehash: eaba6b2166a82cfe825ffb98db515e24d4656462
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138229"
---
# <a name="epolicyaction-enumeration"></a>Перечисление EPolicyAction
Описание действий политики, которые узел может задать для операций, описанных в [еклроператион](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) и ошибках, описанных в [еклрфаилуре](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`eAbortThread`|Указывает, что среда CLR должна корректно прерывать поток. Корректное прерывание включает попытки запуска всех блоков `finally`, любых блоков `catch`, связанных с пределами потоков и методов завершения.|  
|`eDisableRuntime`|Указывает, что среда CLR должна перейти в отключенное состояние. В затронутом процессе не может быть выполнен дальнейший управляемый код, и потокам не удастся войти в среду CLR.|  
|`eExitProcess`|Указывает, что среда CLR должна попытаться корректно выйти из процесса, включая запуск методов завершения и выполнение операций очистки и ведения журнала.|  
|`eFastExitProcess`|Указывает, что среда CLR должна немедленно выйти из процесса, не запуская методы завершения, а также выполнять операции очистки и ведения журнала. Однако уведомление отправляется в отладчик.|  
|`eNoAction`|Указывает, что никакие действия не следует предпринимать.|  
|`eRudeAbortThread`|Указывает, что среда CLR должна выполнять грубое прерывание потока. Выполняются только блоки `catch` и `finally`, помеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute>.|  
|`eRudeExitProcess`|Указывает, что среда CLR должна выйти из процесса без запуска методов завершения или ведения журнала.|  
|`eRudeUnloadAppDomain`|Указывает, что среда CLR должна выполнить грубую выгрузку <xref:System.AppDomain>. Выполняются только методы завершения, помеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute>. Аналогично, все потоки с этим <xref:System.AppDomain> в стеке получают `ThreadAbortException`, но выполняются только блоки `catch` и `finally`, помеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute>.|  
|`eThrowException`|Указывает, что должно быть создано исключение, соответствующее условию, например нехватки памяти, переполнение буфера и т. д.|  
|`eUnloadAppDomain`|Указывает, что <xref:System.AppDomain> должны быть выгружены. Среда CLR пытается запустить методы завершения.|  
  
## <a name="remarks"></a>Заметки  
 Узел задает действия политики, вызывая методы интерфейса [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) . Сведения о принудительном и корректном аварийном завершении см. в разделе Перечисление [еклроператион](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [Интерфейс IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
