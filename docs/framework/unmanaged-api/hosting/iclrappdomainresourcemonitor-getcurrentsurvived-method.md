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
ms.openlocfilehash: 7c179ba23be07e8ff77e1397ed753d4287b22440
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>Метод ICLRAppDomainResourceMonitor::GetCurrentSurvived
Возвращает количество байтов, оставшихся после последней полной, блокирующей сборки мусора и которые ссылается текущий домен приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwAppDomainId`  
 [in] Идентификатор домена запрошенное приложение.  
  
 `pAppDomainBytesSurvived`  
 [out] Указатель на число байтов, оставшихся после последней сборки мусора, удерживаемые этим доменом приложения. После полной сборки мусора это число является точным и полным. После эфемерной сборки мусора это число является потенциально неполным. Этот параметр может иметь значение `null`.  
  
 `pRuntimeBytesSurvived`  
 [out] Указатель на общее число байтов, сохранившихся после последней сборки мусора. После полной сборки мусора это число представляет количество байтов, которые хранятся в управляемых кучах. После эфемерной сборки мусора это число представляет количество байтов, которые хранятся в эфемерных поколениях. Этот параметр может иметь значение `null`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|COR_E_APPDOMAINUNLOADED|Домен приложения выгружен или не существует.|  
  
## <a name="remarks"></a>Примечания  
 Статистические данные обновляются только после полной блокирующей сборки мусора; Другими словами происходит коллекции, включающий все поколения и которая останавливает приложения во время сбора. Например <xref:System.GC.Collect?displayProperty=nameWithType> перегрузка метода выполняет полной блокирующей сборки. Параллельная сборка мусора происходит в фоновом режиме и не блокирует работу приложения.  
  
 `GetCurrentSurvived` Метода эквивалентно неуправляемые управляемый <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> свойство.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRAppDomainResourceMonitor](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [Отслеживание ресурсов домена приложения](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
