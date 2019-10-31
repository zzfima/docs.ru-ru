---
title: Интерфейс ICLRPolicyManager
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
ms.openlocfilehash: 59aa904d4c67326b60381d3476eaab179d7fa42b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140808"
---
# <a name="iclrpolicymanager-interface"></a>Интерфейс ICLRPolicyManager
Предоставляет методы, позволяющие основному приложению указывать действия политики, выполняемые в случае сбоев и истечения времени ожидания.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|Указывает действие политики, которое должна выполнять среда CLR при возникновении указанного сбоя.|  
|[Метод SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|Указывает действие политики, которое должна выполнять среда CLR при истечении времени ожидания указанной операции.|  
|[Метод SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|Указывает действие политики, которое должна выполнять среда CLR при выполнении указанной операции.|  
|[Метод SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|Задает значение времени ожидания для указанной операции.|  
|[Метод SetTimeoutAndAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|Задает значение времени ожидания для указанной операции и указывает действие политики, которое должна выполнять среда CLR при выполнении операции.|  
|[Метод SetUnhandledExceptionPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|Задает поведение среды CLR при возникновении необработанного исключения.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [Перечисление EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [Перечисление EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
