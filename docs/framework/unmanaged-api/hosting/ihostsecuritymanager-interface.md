---
title: Интерфейс IHostSecurityManager
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f45379fe8640ef7e7b3917bac8d10ca956d75ffb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61957590"
---
# <a name="ihostsecuritymanager-interface"></a>Интерфейс IHostSecurityManager
Предоставляет методы, разрешающие доступ к и контроль над контекст безопасности текущего потока.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|Возвращает запрашиваемый [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) с узла.|  
|[Метод ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|Запросы на выполнение кода с использованием учетных данных удостоверения текущего пользователя.|  
|[Метод OpenThreadToken](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|Открывает токена доступа на уровне пользователей, связанный с текущим потоком.|  
|[Метод RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|Завершает олицетворение удостоверения текущего пользователя и возвращает исходный маркер потока.|  
|[Метод SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|Задает контекст безопасности для текущего потока.|  
|[Метод SetThreadToken](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|Задает дескриптор для текущего потока.|  
  
## <a name="remarks"></a>Примечания  
 Узел может управлять всем доступ кода к маркерам потока как среда CLR (CLR), так и пользовательского кода. Также можно обеспечить, полную безопасность сведений о контексте передается через асинхронные операции или кодовые точки с ограниченным доступом. `IHostSecurityContext` инкапсулирует эти сведения о контексте безопасности, который является непрозрачным для среды CLR.  
  
 Среда CLR обрабатывает контекста потока внутренним образом. Он запрашивает относящиеся к процессу `IHostSecurityManager` в следующих ситуациях:  
  
- В потоке метода завершения, во время выполнения метода завершения.  
  
- Во время выполнения конструктор класса и модуля.  
  
- В асинхронные точки в рабочем потоке, в вызовах [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) метод.  
  
- При обслуживании портов завершения ввода-вывода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
