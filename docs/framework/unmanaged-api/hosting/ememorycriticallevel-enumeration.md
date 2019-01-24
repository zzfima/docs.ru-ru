---
title: Перечисление EMemoryCriticalLevel
ms.date: 03/30/2017
api_name:
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: def1c04064cc9fc98c108dcdad5c017c0c8e465b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655534"
---
# <a name="ememorycriticallevel-enumeration"></a>Перечисление EMemoryCriticalLevel
Содержит значения, указывающие влияние сбоя при запросе определенного выделения памяти, не может быть удовлетворен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`eAppDomainCritical`|Указывает, что выделение крайне важен для выполнения управляемого кода в домене, который запросил выделение. Если не удалось выделить память, среда CLR не может гарантировать, что домен является по-прежнему можно использовать. Узел определяет, какое действие следует предпринять, если выделение не может быть удовлетворено. Его можно указать среде CLR прерывание `AppDomain` автоматически, или разрешить его выполнение, вызывая методы [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).|  
|`eProcessCritical`|Указывает, что выделение крайне важен для выполнения управляемого кода в процессе. Это значение используется во время запуска и при выполнении методов завершения. Если не удалось выделить память, среда CLR не может работать в процессе. В случае сбоя, среда CLR эффективно отключено. Все последующие вызовы в среду CLR завершаться значение HOST_E_CLRNOTAVAILABLE.|  
|`eTaskCritical`|Указывает, что выделение крайне важен для выполнения задачи, которая запросила выделение. Если не удалось выделить память, среда CLR не может гарантировать, что задача может выполняться. В случае сбоя среда CLR вызывает <xref:System.Threading.ThreadAbortException> на потоке системы физическая операция.|  
  
## <a name="remarks"></a>Примечания  
 Методы распределения памяти, определенные в [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) и [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) интерфейса принимающие параметр этого типа. В зависимости от серьезности ошибки, узел может решить, следует ли переход на другой запрос на выделение ресурсов немедленно или подождите, пока не может быть удовлетворено.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
