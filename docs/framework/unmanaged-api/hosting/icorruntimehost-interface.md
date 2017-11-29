---
title: "Интерфейс ICorRuntimeHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost
helpviewer_keywords: ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 844648cd2cfafc561e27bea870703ee3a55fb404
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehost-interface"></a>Интерфейс ICorRuntimeHost
Предоставляет методы, позволяющие хост для запуска и остановки общеязыковой среды выполнения (CLR) явным образом, для создания и настройки доменов приложений, для доступа к области по умолчанию и перечисления всех доменов, выполняемых в процессе.  
  
 В платформе .NET Framework версии 2.0 этот интерфейс является внесены [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CloseEnum](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|Сбрасывает перечислитель доменов в начало списка доменов.|  
|[CreateDomain-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|Создает домен приложения. Вызывающий объект получает указатель интерфейса типа <xref:System._AppDomain> к экземпляру типа <xref:System.AppDomain?displayProperty=nameWithType>.|  
|[CreateDomainEx-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|Создает домен приложения. Этот метод позволяет вызывающему объекту передать экземпляр IAppDomainSetup для настройки дополнительных функций возвращенного <xref:System._AppDomain> экземпляра.|  
|[Createdomainsetup-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|Получает указатель интерфейса типа `IAppDomainSetup` для <xref:System.AppDomainSetup> экземпляра. `IAppDomainSetup`Предоставляет методы для настройки аспектов домена приложения перед его созданием.|  
|[Createevidence-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|Получает указатель интерфейса типа <xref:System.Security.Principal.IIdentity>, что позволяет узлу создавать свидетельством безопасности для передачи [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) или [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).|  
|[Createlogicalthreadstate-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|Не используется.|  
|[CurrentDomain-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|Получает указатель интерфейса типа <xref:System._AppDomain> , представляющий домен, который загружен в текущем потоке.|  
|[Deletelogicalthreadstate-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|Не используется.|  
|[Enumdomains-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|Получает перечислитель для доменов в текущем процессе.|  
|[Метод GetConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|Возвращает объект, позволяющий основному приложению задать конфигурацию обратного вызова среды CLR.|  
|[Getdefaultdomain-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|Получает указатель интерфейса типа <xref:System._AppDomain> , представляющий домен по умолчанию для текущего процесса.|  
|[Locksheldbylogicalthread-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|Не используется.|  
|[MapFile-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|Сопоставляет указанный файл в память. Этот метод устарел.|  
|[Nextdomain-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|Получает указатель интерфейса на следующий домен в перечислении.|  
|[Start-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|Запускает среду CLR.|  
|[STOP-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|Останавливает выполнение кода в среде выполнения для текущего процесса.|  
|[Switchinlogicalthreadstate-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|Не используется.|  
|[Switchoutlogicalthreadstate-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|Не используется.|  
|[Unloaddomain-метод](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|Выгружает заданный домен приложения из текущего процесса.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>См. также  
 <xref:System.AppDomain>  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [ICLRRuntimeHost-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [Узлы среды выполнения](http://msdn.microsoft.com/en-us/99d9246a-b994-4fe5-985c-8588d1d59998)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Компонентный класс CorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
