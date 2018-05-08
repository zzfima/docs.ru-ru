---
title: Интерфейс IHostSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c2500f013584ef4722ceaaaee91d5db54991639
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostsecuritycontext-interface"></a>Интерфейс IHostSecurityContext
Позволяет общеязыковая среда выполнения (CLR), чтобы сохранить сведения о контексте безопасности, реализуемых основным приложением.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Capture](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|Возвращает точную копию `IHostSecurityContext` экземпляр возвращен из вызова [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).|  
  
## <a name="remarks"></a>Примечания  
 Узел может управлять доступом кода к маркерам потока из кода среды CLR и пользователя. Также можно обеспечить, полный безопасность Контекстная информация, передаваемая через асинхронные операции или кодовые точки с ограниченным доступом. `IHostSecurityContext` инкапсулирует эти сведения о контексте безопасности, являющиеся непрозрачными для среды выполнения. Среда выполнения перехватывает эти сведения с помощью `Capture`, и перемещает ее через элемент подготовки к отправке рабочего потока пула, выполнение методов завершения и конструкторов класса и модуля.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [Интерфейс IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
