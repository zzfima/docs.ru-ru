---
title: Метод IActionOnCLREvent::OnEvent
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent.OnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28178cca27c257e480a7c5ec87c1925af7de4f78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436420"
---
# <a name="iactiononclreventonevent-method"></a>Метод IActionOnCLREvent::OnEvent
Выполняет обратные вызовы для событий, которые были зарегистрированы с помощью вызова [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `event`  
 [in] Один из [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) значения, которые указывает тип события.  
  
 `data`  
 [in] Указатель на объект, содержащий сведения о `event`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`OnEvent` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы любой метод размещения возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 `data` Параметр является указателем на объект незаданного типа. Если `event` параметр `Event_DomainUnload`, `data` числовой идентификатор <xref:System.AppDomain> , был выгружен. Узел может предпринять соответствующее действие, используя этот идентификатор в качестве ключа.  
  
 Если `event` — `Event_MDAFired`, `data` — это указатель на [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) экземпляру, содержащему вывод сообщений из управляемого помощника по отладке (MDA). MDA — это функция среды CLR, которая помогает разработчикам при отладке, создавая XML-сообщения о событиях, которые в противном случае сложно для перехвата исключения. Такие сообщения могут быть особенно полезен при отладке переходы между управляемым и неуправляемым кодом. Дополнительные сведения см. в разделе [Диагностика ошибок посредством управляемых помощников по отладке](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Перечисление EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [Интерфейс IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Интерфейс ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [Структура MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
