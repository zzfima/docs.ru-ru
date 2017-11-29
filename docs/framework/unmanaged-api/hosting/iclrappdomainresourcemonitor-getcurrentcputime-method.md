---
title: "Метод ICLRAppDomainResourceMonitor::GetCurrentCpuTime"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2483165de54cd5ec76abad9d8472e0deef28f149
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a>Метод ICLRAppDomainResourceMonitor::GetCurrentCpuTime
Возвращает общее процессорное время, использованное всеми потоками при выполнении в текущем домене приложения с момента создания домена приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwAppDomainId`  
 [in] Идентификатор домена запрошенное приложение.  
  
 `pMilliseconds`  
 [out] Указатель на общее процессорное время, использованное всеми потоками при выполнении в текущем домене приложения с момента создания домена приложения. Этот параметр может иметь значение `null`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|COR_E_APPDOMAINUNLOADED|Домен приложения выгружен или не существует.|  
|E_FAIL|Отслеживание ресурсов домена приложения не включен.<br /><br /> -или-<br /><br /> Прочие сбои.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод эквивалентен неуправляемые управляемый <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> свойство.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICLRAppDomainResourceMonitor-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Отслеживание ресурсов домена приложения](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
