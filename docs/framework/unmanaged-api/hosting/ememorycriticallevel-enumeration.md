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
ms.openlocfilehash: 8364d38f7ab81b73fd8b47d2251bc0ff1b2c71e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138249"
---
# <a name="ememorycriticallevel-enumeration"></a>Перечисление EMemoryCriticalLevel
Содержит значения, которые указывают на влияние сбоя при запросе определенного выделения памяти, но не могут быть удовлетворены.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`eAppDomainCritical`|Указывает, что выделение является критически важным для исполнения управляемого кода в домене, который запросил выделение. Если память не может быть выделена, среда CLR не может гарантировать, что домен будет использоваться. Основное приложение принимает решение, какое действие следует предпринять, если выделение не может быть удовлетворено. Он может дать среде CLR команду на автоматическое прерывание `AppDomain` или разрешить ее выполнение путем вызова методов в [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).|  
|`eProcessCritical`|Указывает, что выделение является критически важным для выполнения управляемого кода в процессе. Это значение используется при запуске и при запуске методов завершения. Если память не может быть выделена, среда CLR не может работать в процессе. Если выделение завершается неудачей, среда CLR фактически отключается. Все последующие вызовы среды CLR завершаются сбоем с HOST_E_CLRNOTAVAILABLE.|  
|`eTaskCritical`|Указывает, что выделение является критически важным для выполнения задачи, которая запросила выделение. Если память не может быть выделена, среда CLR не может гарантировать, что задача может быть выполнена. В случае сбоя среда CLR вызывает <xref:System.Threading.ThreadAbortException> в системном потоке физической операции.|  
  
## <a name="remarks"></a>Заметки  
 Методы выделения памяти, определенные в интерфейсах [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) и [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) , принимают параметр этого типа. В зависимости от серьезности сбоя узел может решить, следует ли немедленно выполнить запрос на выделение или подождать, пока он не будет удовлетворен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
