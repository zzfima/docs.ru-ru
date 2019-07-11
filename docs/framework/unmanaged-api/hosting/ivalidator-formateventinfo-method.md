---
title: Метод IValidator::FormatEventInfo
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31329a8674a9991a3f306eeff44ee3437ad64a5c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779436"
---
# <a name="ivalidatorformateventinfo-method"></a>Метод IValidator::FormatEventInfo
Получает сообщение об ошибке, соответствующее указанной ошибкой проверки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `hVECode`  
 [in] Значение HRESULT, который был передан в обработчик ошибок проверки.  
  
 `Context`  
 [in] Объект `VEContext` экземпляр, содержащий контекстные сведения об ошибке проверки.  
  
 `msg`  
 [in, out] Строка, содержащая сообщение об ошибке.  
  
 `ulMaxLength`  
 [in] Максимальная длина сообщения об ошибке.  
  
 `psa`  
 [in] Безопасный массив, содержащий дополнительные параметры, описывающее ошибку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** IValidator.idl в файле IValidator.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
