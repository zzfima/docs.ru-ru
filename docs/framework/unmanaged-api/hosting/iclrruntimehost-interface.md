---
title: Интерфейс ICLRRuntimeHost
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f159c0b57f2087b608fac8cbc9b9c64ceb063a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965995"
---
# <a name="iclrruntimehost-interface"></a>Интерфейс ICLRRuntimeHost
Предоставляет функциональные возможности, аналогичные интерфейсу [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) , предоставленному в .NET Framework версии 1, со следующими изменениями:  
  
- Добавление метода [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) для задания интерфейса элемента управления ведущего приложения.  
  
- Пропуск некоторых методов, `ICorRuntimeHost`предоставляемых.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|Используется в сценариях развертывания ClickOnce на основе манифеста для указания приложения, которое должно быть активировано в новом домене.|  
|[Метод ExecuteInAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|Указывает, <xref:System.AppDomain> в котором следует выполнить указанный управляемый код.|  
|[Метод ExecuteInDefaultAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|Вызывает указанный метод указанного типа в указанной сборке.|  
|[Метод GetCLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|Возвращает указатель интерфейса типа [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , который может использоваться узлами для настройки аспектов среды CLR.|  
|[Метод GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|Возвращает числовой идентификатор <xref:System.AppDomain> объекта, который выполняется в данный момент.|  
|[Метод SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|Задает интерфейс элемента управления ведущего приложения. Перед вызовом `SetHostControl` `Start`необходимо вызвать.|  
|[Метод Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|Инициализирует среду CLR в процессе.|  
|[Метод Stop](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|Останавливает выполнение кода средой выполнения.|  
|[Метод UnloadAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|Выгружает объект <xref:System.AppDomain> , соответствующий указанному числовому идентификатору.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с .NET Framework 4, используйте интерфейс [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) для получения указателя на интерфейс [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) , а затем вызовите метод [ICLRRuntimeInfo::-interface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) , чтобы получить указатель на `ICLRRuntimeHost`. В более ранних версиях .NET Framework узел получает указатель на `ICLRRuntimeHost` экземпляр, вызывая [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или [корбиндтокуррентрунтиме](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md). Чтобы реализовать реализации любой из технологий, предоставляемых в .NET Framework версии 2,0, необходимо использовать `ICLRRuntimeHost` `ICorRuntimeHost`вместо.  
  
> [!IMPORTANT]
> Не вызывайте метод [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) перед вызовом метода [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) для активации приложения на основе манифеста. Если метод вызывается первым, вызов `ExecuteApplication` метода завершится ошибкой. `Start`  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Кокласс CLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
