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
ms.openlocfilehash: a20b79dd5eda9c431511cc49e7e3adaa9486b2aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155991"
---
# <a name="iclrerrorreportingmanager-interface"></a>Интерфейс ICLRErrorReportingManager
Предоставляет методы, позволяющие узла настроить пользовательские дампы стека для отчетов об ошибках.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|Указывает конфигурацию пользовательских дампов стека для отчетов об ошибках.|  
|[Метод EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|Удаляет конфигурацию пользовательского дампа стека, установленное с предыдущими вызовами `BeginCustomDump`.|  
|[Метод GetBucketParametersForCurrentException](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|Возвращает сегмент Watson для текущего исключения в вызывающем потоке.|  
  
## <a name="remarks"></a>Примечания  
 `BeginCustomDump` Метод задает конфигурацию пользовательского дампа стека. `EndCustomDump` Метод очищает конфигурацию пользовательского дампа стека и освобождает все связанные состояния. Он должен вызываться после завершения пользовательского дампа.  
  
> [!IMPORTANT]
>  Сбой при вызове `EndCustomDump` приводит к утечке памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
