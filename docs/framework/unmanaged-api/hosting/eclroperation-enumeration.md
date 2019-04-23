---
title: Перечисление EClrOperation
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d5f24d7415ff7ecceba6b0a5fbd3098d70dcd0f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190357"
---
# <a name="eclroperation-enumeration"></a>Перечисление EClrOperation
Описывает набор операций, для которых узел может применять действия политики.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|Узел может указать политику действий, выполняемых при <xref:System.AppDomain> выгружается образом ненадлежащими (принудительными).|  
|`OPR_AppDomainUnload`|Узел может указать политику действий, выполняемых при <xref:System.AppDomain> выгружается.|  
|`OPR_FinalizerRun`|Узел может указать действия политики, которые необходимо выполнить при запуске метода завершения.|  
|`OPR_ProcessExit`|Узел может указать действия политики, которые должны выполняться при завершении процесса.|  
|`OPR_ThreadAbort`|Узел может указать действия политики, которые должны выполняться при прерывании потока.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|Узел может указать действия политики, которые должны выполняться при грубое прерывание потока происходит в критической области кода.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|Узел может указать политики действия быть при грубое прерывание потока происходит в некритические области кода.|  
  
## <a name="remarks"></a>Примечания  
 Инфраструктуре надежности среды выполнения (CLR) различает прерываний и ресурсов ошибок выделения ресурсов, которые происходят в критических областях кода, и те, которые возникают в некритические областей кода. Это различие позволяет основным приложениям задавать различные политики в зависимости от того, где происходит сбой в коде.  
  
 Объект *критической области кода* любого места, где среда CLR не может гарантировать, что прерывание выполнения задачи или сбой при выполнении запроса для ресурсов повлияет только на текущую задачу. Например, если задача заблокирована и получает значение HRESULT, указывающее на сбой при выполнении запроса на выделение памяти, недостаточно просто прервать эту задачу, чтобы убедиться в стабильной работе <xref:System.AppDomain>, так как <xref:System.AppDomain> может содержать другие элементы задачи, ожидающие ту же блокировку. Прекращение выполнения текущей задачи может привести другие задачи, чтобы перестать отвечать на запросы (или зависанию) неопределенное время. В этом случае узел должен возможность выгрузить весь <xref:System.AppDomain> вместо того чтобы нестабильной работы риска.  
  
 Объект *некритические области кода*, с другой стороны, — это область, в которой среда CLR может гарантировать, что прерывание или сбой повлияют только задачи, на котором произошла ошибка.  
  
 Среда CLR также различает нормальные, так и ненадлежащими (принудительными) прерываниями. В общем случае обычный или корректное прерывание делает все возможное для выполнения подпрограммы обработки исключений и методы завершения перед прекращением задачу, хотя грубые прерывания не обеспечивает таких.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [Перечисление EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [Интерфейс IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
