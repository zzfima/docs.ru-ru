---
title: Метод ICLRAppDomainResourceMonitor::GetCurrentSurvived
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf285b6e1f703c8776937fa33c7ab5801f04f80f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950164"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>Метод ICLRAppDomainResourceMonitor::GetCurrentSurvived
Возвращает число байтов, сохранившихся последней полной блокирующей сборки мусора, на которые ссылается текущий домен приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwAppDomainId`  
 окне ИДЕНТИФИКАТОР запрошенного домена приложения.  
  
 `pAppDomainBytesSurvived`  
 заполняет Указатель на число байтов, сохранившихся после последней сборки мусора, удерживаемых этим доменом приложения. После полного сбора это число является точным и полным. После эфемерной коллекции это число может быть неполным. Этот параметр может иметь значение `null`.  
  
 `pRuntimeBytesSurvived`  
 заполняет Указатель на общее число байтов, сохранившихся из последней сборки мусора. После полной сборки мусора это число представляет число байтов, хранящихся в управляемых кучах. После эфемерной коллекции это число представляет число байтов, которые удерживаются в режиме эфемерного поколения. Этот параметр может иметь значение `null`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|COR_E_APPDOMAINUNLOADED|Домен приложения был выгружен или не существует.|  
  
## <a name="remarks"></a>Примечания  
 Статистика обновляется только после полной блокированной сборки мусора; то есть коллекция, включающая все поколения и останавливающая работу приложения во время сбора. Например, <xref:System.GC.Collect?displayProperty=nameWithType> перегрузка метода выполняет полную блокированную коллекцию. Параллельная сборка мусора выполняется в фоновом режиме и не блокирует приложение.  
  
 Метод является неуправляемым эквивалентом управляемого <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> свойства. `GetCurrentSurvived`  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Метахост. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAppDomainResourceMonitor](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [Отслеживание ресурсов домена приложения](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
