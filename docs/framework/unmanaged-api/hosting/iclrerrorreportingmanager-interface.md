---
title: "Интерфейс ICLRErrorReportingManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager
helpviewer_keywords: ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 590cd87d6a566e9c8c3819fd1b250997938e9c35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrerrorreportingmanager-interface"></a>Интерфейс ICLRErrorReportingManager
Предоставляет методы, позволяющие основному приложению настроить пользовательские дампы стека для отчетов об ошибках.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|Указывает конфигурацию пользовательских дампов стека для отчетов об ошибках.|  
|[EndCustomDump-метод](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|Очищает конфигурацию пользовательского дампа стека, заданные с предыдущими вызовами метода `BeginCustomDump`.|  
|[Getbucketparametersforcurrentexception-метод](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|Получает блок Watson для текущего исключения в вызывающем потоке.|  
  
## <a name="remarks"></a>Примечания  
 `BeginCustomDump` Метод задает конфигурацию пользовательского дампа стека. `EndCustomDump` Метод очищает конфигурацию пользовательского дампа стека и освобождает все связанные состояния. Он должен вызываться после завершения пользовательского дампа.  
  
> [!IMPORTANT]
>  Сбой при вызове `EndCustomDump` вызывает утечку памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Ecustomdumpitemkind-перечисление](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
