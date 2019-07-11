---
title: Метод ICorRuntimeHost::GetDefaultDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetDefaultDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe80050d7b513bce2660b81c5e4faa35b375f22b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780036"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a>Метод ICorRuntimeHost::GetDefaultDomain
Получает указатель интерфейса типа <xref:System._AppDomain?displayProperty=nameWithType> , представляющий домен по умолчанию для текущего процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAppDomain`  
 [out] Указатель интерфейса типа <xref:System._AppDomain?displayProperty=nameWithType> для <xref:System.AppDomain> экземпляр, который представляет домен приложения по умолчанию для процесса.  
  
 Этот указатель является типизированным `IUnknown`, поэтому вызывающие объекты обычно должен вызвать `QueryInterface` для получения указателя интерфейса типа <xref:System._AppDomain?displayProperty=nameWithType>.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Операция выполнена успешно.|  
|S_FALSE|Не удалось завершить операцию.|  
|E_FAIL|Произошла неизвестная, разрушительного сбоя. Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе. Последующие вызовы для любого API хостинга, возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>См. также

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
