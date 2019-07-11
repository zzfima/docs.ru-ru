---
title: Функция _AxlGetIssuerPublicKeyHash
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de55594db68e084009a095a083e065fbd0b8f0df
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741331"
---
# <a name="axlgetissuerpublickeyhash-function"></a>\_Функция AxlGetIssuerPublicKeyHash
Получает хэш SHA-1 открытого ключа, связанного с закрытым ключом, который используется для подписания указанного сертификата.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pChainContext`  
 [в] Большой двоичный объект открытого ключа CSP. См. в разделе [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) структуры.  
  
 `ppwszPublicKeyHash`  
 [из] Указатель на WCHAR * для получения шестнадцатеричного кодированного маркера открытого ключа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`, если функция выполняется успешно. В противном случае — `S_FALSE`.  
  
## <a name="see-also"></a>См. также

- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
