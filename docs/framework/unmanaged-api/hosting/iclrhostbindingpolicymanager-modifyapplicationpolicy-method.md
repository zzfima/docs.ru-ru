---
title: Метод ICLRHostBindingPolicyManager::ModifyApplicationPolicy
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a9e438e6dd436303cd6f7aa60c779179b5d3c04
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779673"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>Метод ICLRHostBindingPolicyManager::ModifyApplicationPolicy
Изменяет политику привязки для указанной сборки и создает новую версию политики.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,   
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,   
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzSourceAssemblyIdentity`  
 [in] Удостоверение сборки для изменения.  
  
 `pwzTargetAssemblyIdentity`  
 [in] Новый идентификатор измененной сборке.  
  
 `pbApplicationPolicy`  
 [in] Указатель на буфер, содержащий данные о политике привязки для сборки для изменения.  
  
 `cbAppPolicySize`  
 [in] Размер политику привязки заменяемого.  
  
 `dwPolicyModifyFlags`  
 [in] Сочетание логического или [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) значения, связанным с управлением перенаправления.  
  
 `pbNewApplicationPolicy`  
 [out] Указатель на буфер, содержащий новые данные о политике привязки.  
  
 `pcbNewAppPolicySize`  
 [in, out] Указатель на размер буфера новой политики привязки.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Политика была успешно изменена.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity` или `pwzTargetAssemblyIdentity` был ссылкой на null.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` слишком мал.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 `ModifyApplicationPolicy` Метод может вызываться дважды. Первый вызов должен предоставить значение null для `pbNewApplicationPolicy` параметра. Этот вызов вернет со значением, необходимые для `pcbNewAppPolicySize`. Второй вызов должен указывать это значение для `pcbNewAppPolicySize`и выберите пункт буфера этого размера для `pbNewApplicationPolicy`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
