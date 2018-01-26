---
title: "Интерфейс IHostSecurityManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager
helpviewer_keywords: IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44f2272c0f4e1423c222a004559d7bbd58237d82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanager-interface"></a>Интерфейс IHostSecurityManager
Предоставляет методы, обеспечивающие доступ и контроль над контекст безопасности текущего потока.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|Возвращает запрошенный [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) хоста.|  
|[Метод ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|Запросы на выполнение кода с использованием учетных данных удостоверения текущего пользователя.|  
|[Метод OpenThreadToken](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|Открывает маркер доступом, связанный с текущим потоком.|  
|[Метод RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|Завершает олицетворение удостоверения текущего пользователя и возвращает исходный маркер потока.|  
|[Метод SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|Задает контекст безопасности для текущего потока.|  
|[Метод SetThreadToken](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|Задает дескриптор для текущего потока.|  
  
## <a name="remarks"></a>Примечания  
 Узел может управлять доступом кода к маркерам потока общеязыковая среда выполнения (CLR) и пользовательского кода. Также можно обеспечить, полный безопасность Контекстная информация, передаваемая через асинхронные операции или кодовые точки с ограниченным доступом. `IHostSecurityContext`инкапсулирует эти сведения о контексте безопасности, являющиеся непрозрачными для среды CLR.  
  
 Среда CLR обрабатывает контекста потока внутренним образом. Он запрашивает относящиеся к процессу `IHostSecurityManager` в следующих ситуациях:  
  
-   В потоке метода завершения во время выполнения метода завершения.  
  
-   Во время выполнения конструктора класса и модуля.  
  
-   В асинхронной точках в рабочем потоке, в вызовах [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) метод.  
  
-   При обслуживании портов завершения ввода-вывода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
