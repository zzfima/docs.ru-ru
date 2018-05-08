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
ms.openlocfilehash: 4b18c89cee0c3f5088a9978e448a0d61de1b9848
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
|`OPR_AppDomainRudeUnload`|Узел может указать действия политики, которые необходимо выполнить при <xref:System.AppDomain> выгружается образом корректное (принудительными).|  
|`OPR_AppDomainUnload`|Узел может указать действия политики, которые необходимо выполнить при <xref:System.AppDomain> выгрузкой.|  
|`OPR_FinalizerRun`|Узел может указать действия политики, которые необходимо выполнить при запуске метода завершения.|  
|`OPR_ProcessExit`|Узел может указать действия политики, которые должны выполняться при завершении процесса.|  
|`OPR_ThreadAbort`|Узел может указать действия политики, которые должны выполняться при прерывании потока.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|Узел может указать действия политики, которые должны выполняться при принудительном прерывании потока в критической области кода.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|Узел может указать действия политики, которые нужно выполнить при принудительном прерывании потока в некритической области кода.|  
  
## <a name="remarks"></a>Примечания  
 Инфраструктуре надежности среды выполнения (CLR) различаются прерываний и ресурсов ошибок выделения, которые происходят в критические области кода, и те, которые возникают в некритической области кода. Это различие позволяет основным приложениям задавать различные политики в зависимости от того, где происходит сбой в коде.  
  
 Объект *критической области кода* любого места, где среда CLR не может гарантировать, что прерывание выполнения задачи или сбой при выполнении запроса для ресурсов повлияет только на текущую задачу. Например, если задача заблокирована и получает значение HRESULT, указывающее на сбой при выполнении запроса на выделение памяти, недостаточно просто отменить эту задачу, чтобы убедиться в стабильной работе <xref:System.AppDomain>, так как <xref:System.AppDomain> может содержать другие задач, ожидающих блокировки. Прекращение выполнения текущей задачи может привести другие задачи, чтобы перестать отвечать на запросы (или зависанию) бесконечно. В этом случае основному приложению возможность выгрузить весь <xref:System.AppDomain> вместо нестабильной риска.  
  
 Объект *некритической области кода*, с другой стороны, — это область, в которых среда CLR может гарантировать, что прерывание или сбой повлияют только задачи, на которой произошла ошибка.  
  
 Среда CLR также проводится различие между корректное и без надлежащих (принудительными) прерываниями. В общем случае обычный или корректное прерывание прилагает все усилия для запуска подпрограммы обработки исключений и методы завершения перед его выполнением, пока ненадлежащее прерывание не дает таких гарантий.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисление EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [Перечисление EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [Интерфейс IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
