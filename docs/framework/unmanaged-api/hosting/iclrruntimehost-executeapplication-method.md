---
title: Метод ICLRRuntimeHost::ExecuteApplication
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38938de335e5f0d7cb8051554c400f16df012362
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965361"
---
# <a name="iclrruntimehostexecuteapplication-method"></a>Метод ICLRRuntimeHost::ExecuteApplication
Используется в сценариях развертывания ClickOnce на основе манифеста для указания приложения, которое должно быть активировано в новом домене. Дополнительные сведения об этих сценариях см. в разделе [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzAppFullName`  
 окне Полное имя приложения, определенное для <xref:System.ApplicationIdentity>.  
  
 `dwManifestPaths`  
 окне Число строк, `ppwzManifestPaths` содержащихся в массиве.  
  
 `ppwzManifestPaths`  
 [в] Необязательно. Массив строк, содержащий пути манифеста для приложения.  
  
 `dwActivationData`  
 окне Число строк, `ppwzActivationData` содержащихся в массиве.  
  
 `ppwzActivationData`  
 [в] Необязательно. Массив строк, содержащий данные активации приложения, такие как часть строки запроса URL-адреса для приложений, развернутых через Интернет.  
  
 `pReturnValue`  
 заполняет Значение, возвращаемое из точки входа приложения.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`ExecuteApplication`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 `ExecuteApplication`используется для активации приложений ClickOnce в только что созданном домене приложения.  
  
 Параметру `pReturnValue` Output задается значение, возвращаемое приложением. Если для `pReturnValue` `ExecuteApplication` задано значение null, то не завершается ошибкой, но не возвращает значение.  
  
> [!IMPORTANT]
> Не вызывайте метод [метода Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) перед вызовом `ExecuteApplication` метода для активации приложения на основе манифеста. Если метод вызывается первым, вызов `ExecuteApplication` метода завершится ошибкой. `Start`  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [Интерфейс ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [Метод SetAppDomainManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [Пошаговое руководство: Загрузка сборок по требованию с помощью API развертывания ClickOnce с использованием конструктора](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
