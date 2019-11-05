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
ms.openlocfilehash: 9600573a0a730cee10247d5644d587e75856cdd9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141180"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a>Метод ICLRHostBindingPolicyManager::EvaluatePolicy
Оценивает политику привязки от имени узла.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzReferenceIdentity`  
 окне Ссылка на сборку перед вычислением политики.  
  
 `pbApplicationPolicy`  
 окне Указатель на буфер, содержащий данные политики.  
  
 `cbAppPolicySize`  
 окне Размер буфера `pbApplicationPolicy`.  
  
 `pwzPostPolicyReferenceIdentity`  
 заполняет Ссылка на сборку после вычисления новых данных политики.  
  
 `pcchPostPolicyReferenceIdentity`  
 [вход, выход] Указатель на размер буфера ссылки идентификации сборки после вычисления новых данных политики.  
  
 `pdwPoliciesApplied`  
 заполняет Указатель на логическое или сочетание значений [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) , указывающих, какие политики были применены.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Оценка успешно завершена.|  
|E_INVALIDARG|Либо `pwzReferenceIdentity`, либо `pbApplicationPolicy` является пустой ссылкой.|  
|ERROR_INSUFFICIENT_BUFFER|`cbAppPolicySize` слишком мал.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Заметки  
 Метод `EvaluatePolicy` позволяет основному приложению оказывать влияние на политику привязки для поддержки требований к версии сборки, относящейся к конкретному узлу. Сам модуль политики остается внутри среды CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
