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
ms.openlocfilehash: b197aa539e60a9dbcee55cf190c44b45da3a5fb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402019"
---
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="27113-102">Функция _AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="27113-102">_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="27113-103">Получает хэш SHA-1 открытого ключа, связанного с закрытым ключом, который используется для подписания указанного сертификата.</span><span class="sxs-lookup"><span data-stu-id="27113-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27113-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27113-104">Syntax</span></span>  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27113-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27113-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="27113-106">[в] Большой двоичный объект открытого ключа CSP.</span><span class="sxs-lookup"><span data-stu-id="27113-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="27113-107">В разделе [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="27113-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="27113-108">[из] Указатель на WCHAR \* для получения шестнадцатеричного кодированного маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="27113-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27113-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="27113-109">Return Value</span></span>  
 <span data-ttu-id="27113-110">`S_OK`, если функция выполняется успешно. В противном случае — `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="27113-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27113-111">См. также</span><span class="sxs-lookup"><span data-stu-id="27113-111">See Also</span></span>  
 [<span data-ttu-id="27113-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="27113-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
