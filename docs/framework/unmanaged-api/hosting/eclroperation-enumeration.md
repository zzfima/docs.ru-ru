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
ms.openlocfilehash: 6becc44b061ff2baac63437b6a72375d1c3735b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131164"
---
# <a name="eclroperation-enumeration"></a>Перечисление EClrOperation
Описывает набор операций, для которых узел может применять действия политики.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|Узел может указывать действия политики, которые будут выполняться, когда <xref:System.AppDomain> выгружается ненадлежащим образом (принудительно).|  
|`OPR_AppDomainUnload`|Узел может указывать действия политики, выполняемые при выгрузке <xref:System.AppDomain>.|  
|`OPR_FinalizerRun`|Узел может указывать действия политики, выполняемые при выполнении методов завершения.|  
|`OPR_ProcessExit`|Узел может указывать действия политики, выполняемые при завершении процесса.|  
|`OPR_ThreadAbort`|Узел может указывать действия политики, выполняемые при прерывании потока.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|Узел может указывать действия политики, выполняемые при выполнении грубого прерывания потока в критической области кода.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|Узел может указать действия политики, которые должны выполняться, когда грубое прерывание потока происходит в некритической области кода.|  
  
## <a name="remarks"></a>Заметки  
 Инфраструктура надежности среды CLR различает прерывания и сбои выделения ресурсов, происходящие в критических областях кода и происходящих в некритических областях кода. Это различие состоит в том, что узлы могут задавать разные политики в зависимости от того, где происходит сбой в коде.  
  
 *Критическая область кода* — это любое пространство, в котором среда CLR не может гарантировать, что прерывание задачи или невозможность завершения запроса ресурсов повлияет только на текущую задачу. Например, если задача удерживает блокировку и получает значение HRESULT, которое указывает на сбой при выполнении запроса на выделение памяти, недостаточно просто прервать эту задачу, чтобы обеспечить стабильность <xref:System.AppDomain>, поскольку <xref:System.AppDomain> может содержать другие задачи. Ожидание той же блокировки. Чтобы отказаться от текущей задачи, может привести к тому, что другие задачи перестанут отвечать на запросы. В этом случае ведущему приложению требуется возможность выгрузить всю <xref:System.AppDomain>, а не риск потенциальной нестабильной работы.  
  
 С другой стороны, *некритическая область кода*— это регион, в котором CLR может гарантировать, что прерывание или сбой повлияет только на задачу, на которой возникла ошибка.  
  
 Среда CLR также различает корректное и некорректное (принудительное) прерывание. Как правило, обычное или корректное прерывание делает все усилия для выполнения подпрограмм обработки исключений и методов завершения перед прерыванием задачи, в то время как грубое прерывание не делает таких гарантий.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [Перечисление EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [Интерфейс IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
