---
title: Метод ICLRValidator::Validate
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
ms.openlocfilehash: 427895ffea94e6c657d775ebdeb8571070a61c6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178064"
---
# <a name="iclrvalidatorvalidate-method"></a>Метод ICLRValidator::Validate
Проверяет портативный исполняемый (PE) или промежуточный язык Microsoft (MSIL) в указанном файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);
```  
  
## <a name="parameters"></a>Параметры  
 `veh`  
 (в) Указатель на `IVEHandler` экземпляр, обрабатывая ошибки проверки.  
  
 `ulAppDomainId`  
 (в) Идентификатор <xref:System.AppDomain>для текущего .  
  
 `ulFlags`  
 (в) Комбинация значений [ValidatorFlags,](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) указывающая на вид проверки, которая должна быть выполнена.  
  
 `ulMaxError`  
 (в) Максимальное количество ошибок, которые можно разрешить перед выходом из проверки.  
  
 `token`  
 [in] Не используется.  
  
 `fileName`  
 (в) Имя файла, которое должно быть проверено.  
  
 `pe`  
 (в) Указатель на буфер файла.  
  
 `ulSize`  
 (в) Размер файла, в байтах, должен быть проверен.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`Validate`вернулся успешно.|  
|HOST_E_CLRNOTAVAILABLE|Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Вызов приурочен.|  
|HOST_E_NOT_OWNER|Звонящее не владеет замком.|  
|HOST_E_ABANDONED|Событие было отменено в то время как заблокированный поток или волокно ждало на нем.|  
|E_FAIL|Произошел неизвестный катастрофический сбой. Когда метод возвращается E_FAIL, CLR больше не используется в процессе. Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** IValidator.idl, IValidator.h  
  
 **Библиотека:** Включено в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRValidator](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
