---
title: Кокласс CLRRuntimeHost
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bae2d134c412023d0f126453b5285662d994c78
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207764"
---
# <a name="clrruntimehost-coclass"></a>Кокласс CLRRuntimeHost
Предоставляет интерфейсы для выполнения управляемого кода средой выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a>интерфейсов,  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|[Интерфейс ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|Предоставляет методы для управления выполнением приложений средой выполнения.|  
|[Интерфейс ICLRValidator](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|Предоставляет методы для проверки переносимого исполняемого образа и подробные отчеты об ошибках проверки.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.idl  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение коклассов](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
