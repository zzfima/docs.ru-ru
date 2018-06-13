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
ms.openlocfilehash: cf2c343db459879ca95372e104aee68b22dee6b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440621"
---
# <a name="ivalidatorvalidate-method"></a>Метод IValidator::Validate
Проверяет заданный переносимый исполняемый (PE) или файл Microsoft промежуточного языка MSIL.  
  
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
  
#### <a name="parameters"></a>Параметры  
 `veh`  
 [in] Указатель на `IVEHandler` экземпляр, который обрабатывает ошибки проверки.  
  
 `pAppDomain`  
 [in] Указатель на домен приложения, в которой загружается указанный файл.  
  
 `ulFlags`  
 [in] Побитовое сочетание [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) значений, указывающее, проверки, которые необходимо выполнить.  
  
 `ulMaxError`  
 [in] Максимальное число ошибок, чтобы перед выходом из проверки.  
  
 `token`  
 [in] Не используется.  
  
 `fileName`  
 [in] Строка, указывающая имя файла, который необходимо проверить.  
  
 `pe`  
 [in] Указатель на буфер памяти, в которой хранится файл.  
  
 `ulSize`  
 [in] Размер в байтах файла, который необходимо проверить.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** IValidator.idl, IValidator.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 
