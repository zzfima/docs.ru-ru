---
title: "Интерфейс ICLRRuntimeHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost
helpviewer_keywords: ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type: apiref
caps.latest.revision: "26"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 332db2680ca23f34893a6c50c5311d73838bc1e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehost-interface"></a>Интерфейс ICLRRuntimeHost
Предоставляет функциональные возможности аналогичны [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) интерфейс, предоставляемый в .NET Framework версии 1, со следующими изменениями:  
  
-   Добавление [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) метод, чтобы задать интерфейс управления узла.  
  
-   Упущение некоторые методы, предоставляемые `ICorRuntimeHost`.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[ExecuteApplication-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|Используется в сценариях развертывания служб на основе манифестов ClickOnce укажите приложение, которое необходимо активировать в новом домене.|  
|[ExecuteInAppDomain-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|Указывает <xref:System.AppDomain> в которой выполняется указанный управляемый код.|  
|[Executeindefaultappdomain-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|Вызывает указанный метод заданного типа в заданной сборке.|  
|[Getclrcontrol-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|Получает указатель интерфейса типа [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , узлы можно использовать для настройки аспектов среды common language runtime (CLR).|  
|[GetCurrentAppDomainId-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|Возвращает числовой идентификатор <xref:System.AppDomain> , выполняемый в текущий момент.|  
|[SetHostControl-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|Задает интерфейс управления узла. Необходимо вызвать `SetHostControl` перед вызовом `Start`.|  
|[Start-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|Инициализирует среду CLR в процесс.|  
|[STOP-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|Останавливает выполнение кода средой выполнения.|  
|[UnloadAppDomain-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|Выгружает <xref:System.AppDomain> , соответствующий указанный числовой идентификатор.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], используйте [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) интерфейс для получения указателя на [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс, а затем вызвать [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) метод, чтобы получить указатель на `ICLRRuntimeHost`. В более ранних версиях платформы .NET Framework узел получает указатель на `ICLRRuntimeHost` экземпляр путем вызова [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md). Для предоставления реализации любого из технологий, предоставляемых в .NET Framework версии 2.0, необходимо использовать `ICLRRuntimeHost` вместо `ICorRuntimeHost`.  
  
> [!IMPORTANT]
>  Не вызывайте [запустить](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) метод перед вызовом метода [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) метода активации приложения на основе манифеста. Если `Start` сначала вызывается метод `ExecuteApplication` вызов метода завершится ошибкой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Corbindtocurrentruntime-функция](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [CorBindToRuntimeEx-функция](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [ICLRControl-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICorRuntimeHost-интерфейс](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Clrruntimehost-компонентный класс](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
