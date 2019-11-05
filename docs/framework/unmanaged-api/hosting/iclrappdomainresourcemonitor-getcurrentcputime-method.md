---
title: Метод ICLRAppDomainResourceMonitor::GetCurrentCpuTime
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
ms.openlocfilehash: de57fec05c338e51d0691ccfa0d0bffb334848de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126788"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a>Метод ICLRAppDomainResourceMonitor::GetCurrentCpuTime
Возвращает общее время процессора, которое использовалось всеми потоками во время выполнения в текущем домене приложения, так как был создан домен приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwAppDomainId`  
 окне ИДЕНТИФИКАТОР запрошенного домена приложения.  
  
 `pMilliseconds`  
 заполняет Указатель на общее время процессора, которое использовалось всеми потоками при выполнении в текущем домене приложения с момента создания домена приложения. Этот параметр может иметь значение `null`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|COR_E_APPDOMAINUNLOADED|Домен приложения был выгружен или не существует.|  
|E_FAIL|Отслеживание ресурсов домена приложений не включено.<br /><br /> \- или -<br /><br /> Все остальные сбои.|  
  
## <a name="remarks"></a>Заметки  
 Этот метод является неуправляемым эквивалентом управляемого свойства <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAppDomainResourceMonitor](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Отслеживание ресурсов домена приложения](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
