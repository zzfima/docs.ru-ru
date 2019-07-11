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
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="cd9f9-102">\_Функция AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="cd9f9-102">\_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="cd9f9-103">Получает хэш SHA-1 открытого ключа, связанного с закрытым ключом, который используется для подписания указанного сертификата.</span><span class="sxs-lookup"><span data-stu-id="cd9f9-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd9f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd9f9-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd9f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cd9f9-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="cd9f9-106">[в] Большой двоичный объект открытого ключа CSP.</span><span class="sxs-lookup"><span data-stu-id="cd9f9-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="cd9f9-107">См. в разделе [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) структуры.</span><span class="sxs-lookup"><span data-stu-id="cd9f9-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="cd9f9-108">[из] Указатель на WCHAR \* для получения шестнадцатеричного кодированного маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="cd9f9-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd9f9-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cd9f9-109">Return Value</span></span>  
 <span data-ttu-id="cd9f9-110">`S_OK`, если функция выполняется успешно. В противном случае — `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="cd9f9-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9f9-111">См. также</span><span class="sxs-lookup"><span data-stu-id="cd9f9-111">See also</span></span>

- [<span data-ttu-id="cd9f9-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="cd9f9-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
