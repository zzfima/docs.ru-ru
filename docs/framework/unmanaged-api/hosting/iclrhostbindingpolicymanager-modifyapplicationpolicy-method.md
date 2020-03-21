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
ms.openlocfilehash: d8df78e3d5cebe5378dfba11dc0ea93cc8e346eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178101"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>Метод ICLRHostBindingPolicyManager::ModifyApplicationPolicy
Изменяет обязательную политику для указанной сборки и создает новую версию политики.  
  
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
 (в) Идентификация сборки для изменения.  
  
 `pwzTargetAssemblyIdentity`  
 (в) Новая идентичность модифицированной сборки.  
  
 `pbApplicationPolicy`  
 (в) Указатель на буфер, содержащий обязательные данные политики для сборки для изменения.  
  
 `cbAppPolicySize`  
 (в) Размер обязательной политики, подавивающей на замену.  
  
 `dwPolicyModifyFlags`  
 (в) Логическое или сочетание значений [EHostBindingPolicyModifyFlags,](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) указывающих на контроль перенаправления.  
  
 `pbNewApplicationPolicy`  
 (ваут) Указатель на буфер, содержащий новые обязательные данные политики.  
  
 `pcbNewAppPolicySize`  
 (в, вне) Указатель на размер нового обязательного буфера политики.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Политика была успешно изменена.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity`или `pwzTargetAssemblyIdentity` была нулевая ссылка.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` слишком мал.|  
|HOST_E_CLRNOTAVAILABLE|Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Вызов приурочен.|  
|HOST_E_NOT_OWNER|Звонящее не владеет замком.|  
|HOST_E_ABANDONED|Событие было отменено в то время как заблокированный поток или волокно ждало на нем.|  
|E_FAIL|Произошел неизвестный катастрофический сбой. После того, как метод возвращается E_FAIL, CLR больше не может быть пригодным к удочку в процессе. Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  
 Метод `ModifyApplicationPolicy` можно вызвать дважды. Первый вызов должен предоставить `pbNewApplicationPolicy` нулевую стоимость параметра. Этот вызов будет возвращаться `pcbNewAppPolicySize`с необходимым значением для . Второй вызов должен предоставить `pcbNewAppPolicySize`это значение для, и `pbNewApplicationPolicy`указать на буфер такого размера для .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** Включено в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
