---
title: "Функция _AxlGetIssuerPublicKeyHash"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _AxlGetIssuerPublicKeyHash
api_location: clr.dll
api_type: DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 38be1f621425797e27fc41cb3192a628ebbfdb0c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="3bae3-102">Функция _AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="3bae3-102">_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="3bae3-103">Получает хэш SHA-1 открытого ключа, связанного с закрытым ключом, который используется для подписания указанного сертификата.</span><span class="sxs-lookup"><span data-stu-id="3bae3-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bae3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3bae3-104">Syntax</span></span>  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3bae3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3bae3-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="3bae3-106">[в] Большой двоичный объект открытого ключа CSP.</span><span class="sxs-lookup"><span data-stu-id="3bae3-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="3bae3-107">В разделе [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="3bae3-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="3bae3-108">[из] Указатель на WCHAR * для получения шестнадцатеричного кодированного маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="3bae3-108">[out] A pointer to WCHAR * to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bae3-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3bae3-109">Return Value</span></span>  
 <span data-ttu-id="3bae3-110">`S_OK`, если функция выполняется успешно. В противном случае — `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="3bae3-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bae3-111">См. также</span><span class="sxs-lookup"><span data-stu-id="3bae3-111">See Also</span></span>  
 [<span data-ttu-id="3bae3-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="3bae3-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
