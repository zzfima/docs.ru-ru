---
title: Метод IValidator::Validate
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
ms.openlocfilehash: 8ae47eac713fbee30ea543538957b12460b8e1fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123274"
---
# <a name="ivalidatorvalidate-method"></a>Метод IValidator::Validate
Проверяет указанный переносимый исполняемый (PE) или промежуточный язык MSIL-файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `veh`  
 окне Указатель на экземпляр `IVEHandler`, который обрабатывает ошибки проверки.  
  
 `pAppDomain`  
 окне Указатель на домен приложения, в который загружается файл.  
  
 `ulFlags`  
 окне Побитовое сочетание значений [валидаторфлагс](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) , указывающее, какие проверки должны быть выполнены.  
  
 `ulMaxError`  
 окне Максимальное число ошибок, которое необходимо разрешить перед выходом из проверки.  
  
 `token`  
 окне Не используется.  
  
 `fileName`  
 окне Строка, указывающая имя проверяемого файла.  
  
 `pe`  
 окне Указатель на буфер памяти, в котором хранится файл.  
  
 `ulSize`  
 окне Размер проверяемого файла в байтах.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** IValidator. idl, IValidator. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
