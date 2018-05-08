---
title: Интерфейс ICLRErrorReportingManager
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf9e04ed1d3a68fed120c4c13ad992af1f777244
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrerrorreportingmanager-interface"></a>Интерфейс ICLRErrorReportingManager
Предоставляет методы, позволяющие основному приложению настроить пользовательские дампы стека для отчетов об ошибках.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|Указывает конфигурацию пользовательских дампов стека для отчетов об ошибках.|  
|[Метод EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|Очищает конфигурацию пользовательского дампа стека, заданные с предыдущими вызовами метода `BeginCustomDump`.|  
|[Метод GetBucketParametersForCurrentException](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|Получает блок Watson для текущего исключения в вызывающем потоке.|  
  
## <a name="remarks"></a>Примечания  
 `BeginCustomDump` Метод задает конфигурацию пользовательского дампа стека. `EndCustomDump` Метод очищает конфигурацию пользовательского дампа стека и освобождает все связанные состояния. Он должен вызываться после завершения пользовательского дампа.  
  
> [!IMPORTANT]
>  Сбой при вызове `EndCustomDump` вызывает утечку памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисление ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
