---
title: Метод ICLRHostBindingPolicyManager::EvaluatePolicy
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 970e57e3caee7631c8e85aef428df52ec293b9cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648814"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a>Метод ICLRHostBindingPolicyManager::EvaluatePolicy
Оценивает политику привязки от имени узла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pwzReferenceIdentity`  
 [in] Ссылка на сборку до вычисления политики.  
  
 `pbApplicationPolicy`  
 [in] Указатель на буфер, содержащий данные о политике.  
  
 `cbAppPolicySize`  
 [in] Размер `pbApplicationPolicy` буфера.  
  
 `pwzPostPolicyReferenceIdentity`  
 [out] Ссылка на сборку после оценки новых данных политики.  
  
 `pcchPostPolicyReferenceIdentity`  
 [in, out] Указатель на размер буфера ссылку удостоверение сборки после оценки новых данных политики.  
  
 `pdwPoliciesApplied`  
 [out] Указатель на сочетание логического или [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) значения, указывающие, какие политики применены.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Оценка успешно завершена.|  
|E_INVALIDARG|Либо `pwzReferenceIdentity` или `pbApplicationPolicy` является пустой ссылкой.|  
|ERROR_INSUFFICIENT_BUFFER|`cbAppPolicySize` слишком мал.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 `EvaluatePolicy` Метод позволяет узлу, на которые влияют на политику привязки для конкретного узла сборки требования к управлению версиями. Сам обработчик политик остается в среде CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
