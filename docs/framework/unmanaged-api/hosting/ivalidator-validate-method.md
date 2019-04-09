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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1fba06360a0c31e0a7fa3e61de9793bad14650fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127508"
---
# <a name="ivalidatorvalidate-method"></a>Метод IValidator::Validate
Проверяет указанный переносимого исполняемого (PE) или файл Microsoft промежуточного языка MSIL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
 [in] Указатель на `IVEHandler` экземпляр, который обрабатывает ошибки проверки.  
  
 `pAppDomain`  
 [in] Указатель на область приложений, в котором загружается файл.  
  
 `ulFlags`  
 [in] Побитовое сочетание [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) значений, указывающее, проверки, которые должны выполняться.  
  
 `ulMaxError`  
 [in] Максимальное количество ошибок, чтобы разрешить перед выходом из проверки.  
  
 `token`  
 [in] Не используется.  
  
 `fileName`  
 [in] Строка, указывающая имя файла для проверки.  
  
 `pe`  
 [in] Указатель на буфер памяти, в которой будет храниться файл.  
  
 `ulSize`  
 [in] Размер в байтах файла для проверки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** IValidator.idl в файле IValidator.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
