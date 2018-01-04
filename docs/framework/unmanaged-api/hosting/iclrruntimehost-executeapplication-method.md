---
title: "Метод ICLRRuntimeHost::ExecuteApplication"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.ExecuteApplication
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b765f020bd15fa94fb18a6fd7d81cf66c534639
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostexecuteapplication-method"></a>Метод ICLRRuntimeHost::ExecuteApplication
Используется в сценариях развертывания служб на основе манифестов ClickOnce укажите приложение, которое необходимо активировать в новом домене. Дополнительные сведения об этих сценариях см. в разделе [развертывание и безопасность технологии ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pwzAppFullName`  
 [in] Полное имя приложения, как это определено для <xref:System.ApplicationIdentity>.  
  
 `dwManifestPaths`  
 [in] Число строк, содержащихся в `ppwzManifestPaths` массива.  
  
 `ppwzManifestPaths`  
 [в] Необязательно. Строковый массив, содержащий путями манифеста приложения.  
  
 `dwActivationData`  
 [in] Число строк, содержащихся в `ppwzActivationData` массива.  
  
 `ppwzActivationData`  
 [в] Необязательно. Строковый массив, содержащий данные активации приложения, такие как часть строки запроса URL-адрес приложения, развернутые через Интернет.  
  
 `pReturnValue`  
 [out] Значение, возвращаемое точкой входа приложения.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`ExecuteApplication`успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 `ExecuteApplication`используется для активации приложений ClickOnce в новом домене приложения.  
  
 `pReturnValue` Выходного параметра присваивается значение, возвращенное приложением. Если указать значение null для `pReturnValue`, `ExecuteApplication` не завершается ошибкой, но не возвращает значение.  
  
> [!IMPORTANT]
>  Не вызывайте [метод Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) метод перед вызовом метода `ExecuteApplication` метода активации приложения на основе манифеста. Если `Start` сначала вызывается метод `ExecuteApplication` вызов метода завершится ошибкой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.ActivationContext>  
 <xref:System.AppDomainManager>  
 <xref:System.ApplicationIdentity>  
 [Интерфейс ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [Метод SetAppDomainManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)  
 [Пошаговое руководство. Загрузка сборок по требованию с помощью API развертывания ClickOnce с использованием конструктора](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
