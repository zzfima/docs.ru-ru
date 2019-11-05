---
title: Перечисление EClrFailure
ms.date: 03/30/2017
api_name:
- EClrFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrFailure
helpviewer_keywords:
- EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type:
- apiref
ms.openlocfilehash: 7d935bff023d806cf8cfb6d87bde0f82666b51b5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131123"
---
# <a name="eclrfailure-enumeration"></a>Перечисление EClrFailure
Описывает набор сбоев, для которых узел может задавать действия политики.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|Произошла ошибка при попытке выделения ресурса (например, потока, блока памяти или блокировки) в некритической области кода.|  
|`FAIL_CriticalResource`|Произошла ошибка при попытке выделения ресурса (например, потока, блока памяти или блокировки) в критической области кода.|  
|`FAIL_FatalRuntime`|Общеязыковая среда выполнения (CLR) больше не может выполнять управляемый код в процессе. Исходя этого, вызовы любых функций размещения возвращают значение HRESULT, равное HOST_E_CLRNOTAVAILABLE.|  
|`FAIL_OrphanedLock`|Потоку не удалось снять блокировку после возврата из объекта <xref:System.AppDomain>. Узлу не удается установить этот сбой, чтобы привести к прерыванию потока.|  
|`FAIL_StackOverflow`|Произошло переполнение стека.|  
|`FAIL_AccessViolation`|Предпринята попытка чтения или записи в защищенную память. Не поддерживается в .NET Framework 4.|  
|`FAIL_CodeContract`|Ошибка контракта кода. См. раздел [контракты кода](../../../../docs/framework/debug-trace-profile/code-contracts.md).|  
  
## <a name="remarks"></a>Заметки  
 Список значений [еполициактион](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , которые узел может использовать для указания действий политики для условий сбоя, см. в описании метода [ICLRPolicyManager:: сетактиононфаилуре](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) . Дополнительные сведения о критических и некритических областях кода см. в разделе [еклроператион](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [Метод SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)
- [Интерфейс IHostPolicyManager](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
