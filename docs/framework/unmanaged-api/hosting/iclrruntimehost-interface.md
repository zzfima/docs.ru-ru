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
ms.openlocfilehash: 568c63681b84d0ab3642d84e4a6715ad230582db
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120392"
---
# <a name="iclrruntimehost-interface"></a>Интерфейс ICLRRuntimeHost
Предоставляет функциональные возможности, аналогичные интерфейсу [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) , предоставленному в .NET Framework версии 1, со следующими изменениями:  
  
- Добавление метода [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) для задания интерфейса элемента управления ведущего приложения.  
  
- Упущение некоторых методов, предоставляемых `ICorRuntimeHost`.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|Используется в сценариях развертывания ClickOnce на основе манифеста для указания приложения, которое должно быть активировано в новом домене.|  
|[Метод ExecuteInAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|Указывает <xref:System.AppDomain>, в котором будет выполняться указанный управляемый код.|  
|[Метод ExecuteInDefaultAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|Вызывает указанный метод указанного типа в указанной сборке.|  
|[Метод GetCLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|Возвращает указатель интерфейса типа [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , который может использоваться узлами для настройки аспектов среды CLR.|  
|[Метод GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|Возвращает числовой идентификатор <xref:System.AppDomain>, который выполняется в данный момент.|  
|[Метод SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|Задает интерфейс элемента управления ведущего приложения. Необходимо вызвать метод `SetHostControl` перед вызовом `Start`.|  
|[Метод Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|Инициализирует среду CLR в процессе.|  
|[Метод Stop](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|Останавливает выполнение кода средой выполнения.|  
|[Метод UnloadAppDomain](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|Выгружает <xref:System.AppDomain>, соответствующий указанному числовому идентификатору.|  
  
## <a name="remarks"></a>Заметки  
 Начиная с .NET Framework 4, используйте интерфейс [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) для получения указателя на интерфейс [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) , а затем вызовите метод [ICLRRuntimeInfo::](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) webmethod, чтобы получить указатель на `ICLRRuntimeHost`. В более ранних версиях .NET Framework узел получает указатель на экземпляр `ICLRRuntimeHost`, вызывая [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или [корбиндтокуррентрунтиме](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md). Для реализации любых технологий, предоставляемых в .NET Framework версии 2,0, необходимо использовать `ICLRRuntimeHost` вместо `ICorRuntimeHost`.  
  
> [!IMPORTANT]
> Не вызывайте метод [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) перед вызовом метода [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) для активации приложения на основе манифеста. Если метод `Start` вызывается первым, вызов метода `ExecuteApplication` завершится ошибкой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Кокласс CLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
