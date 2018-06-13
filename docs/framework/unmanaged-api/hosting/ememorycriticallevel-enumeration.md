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
ms.openlocfilehash: acf4f3f582e417c5e7b814622986427f996796ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432535"
---
# <a name="ememorycriticallevel-enumeration"></a>Перечисление EMemoryCriticalLevel
Содержит значения, указывающие влияние сбоя в случае, когда был запрошен определенного выделения памяти, но не может быть удовлетворен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`eAppDomainCritical`|Указывает, что выделение крайне важен для выполнения управляемого кода в домене, который запросил распределения. Если не удается выделить память, среда CLR не может гарантировать, что домен является по-прежнему можно использовать. Основное приложение выбирает, какие действия предпринять, если выделение не может быть удовлетворено. Его можно указать среде CLR прерывание `AppDomain` автоматически, или разрешить его выполнение, вызывая методы [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).|  
|`eProcessCritical`|Указывает, что выделение крайне важен для выполнения управляемого кода в процессе. Это значение используется во время запуска и при выполнении методов завершения. Если не удается выделить память, среда CLR не может работать в процессе. В случае сбоя, среда CLR полностью отключается. Все последующие вызовы к CLR завершаться значение HOST_E_CLRNOTAVAILABLE.|  
|`eTaskCritical`|Указывает, что выделение крайне важен для выполнения задачи, запросившей выделение. Если не удается выделить память, среда CLR не гарантирует выполнения задачи. В случае сбоя, среда CLR вызывает <xref:System.Threading.ThreadAbortException> в потоке физическая операция системы.|  
  
## <a name="remarks"></a>Примечания  
 Методы распределения памяти, определенные в [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) и [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) интерфейсы могут принимать параметр этого типа. В зависимости от серьезности сбоя узла можно моментально завершаются ошибкой запросов на выделение или подождите, пока не может быть удовлетворено.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
