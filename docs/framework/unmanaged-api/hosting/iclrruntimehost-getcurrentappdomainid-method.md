---
title: Метод ICLRRuntimeHost::GetCurrentAppDomainId
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbe6ac3c9f03de2224f933a7e44325f578ded48b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433915"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a>Метод ICLRRuntimeHost::GetCurrentAppDomainId
Возвращает числовой идентификатор <xref:System.AppDomain> , выполняемый в текущий момент.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pdwAppDomainId`  
 [out] Числовой идентификатор <xref:System.AppDomain> , выполняемый в текущий момент.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`GetCurrentAppDomainId` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 `pdwAppDomainId` Установлено значение <xref:System.AppDomain.Id%2A> свойство <xref:System.AppDomain> , в которой выполняется текущий поток.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.AppDomain>  
 <xref:System.AppDomainManager>  
 [Интерфейс ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
