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
ms.openlocfilehash: d5323538447e083a0c727e43261dd68337182b9b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141074"
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
 окне Идентификатор сборки, которую необходимо изменить.  
  
 `pwzTargetAssemblyIdentity`  
 окне Новое удостоверение измененной сборки.  
  
 `pbApplicationPolicy`  
 окне Указатель на буфер, содержащий данные политики привязки для изменяемой сборки.  
  
 `cbAppPolicySize`  
 окне Размер заменяемой политики привязки.  
  
 `dwPolicyModifyFlags`  
 окне Логическое или сочетание значений [ехостбиндингполицимодифифлагс](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) , указывающее на контроль перенаправления.  
  
 `pbNewApplicationPolicy`  
 заполняет Указатель на буфер, содержащий новые данные политики привязки.  
  
 `pcbNewAppPolicySize`  
 [вход, выход] Указатель на размер нового буфера политики привязки.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Политика успешно изменена.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity` или `pwzTargetAssemblyIdentity` была пустой ссылкой.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` слишком мал.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Заметки  
 Метод `ModifyApplicationPolicy` можно вызывать дважды. Первый вызов должен предоставить значение NULL для параметра `pbNewApplicationPolicy`. Этот вызов возвратит с требуемым значением для `pcbNewAppPolicySize`. Второй вызов должен предоставить это значение для `pcbNewAppPolicySize`и указать буфер этого размера для `pbNewApplicationPolicy`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
