---
title: Функция _AxlPublicKeyBlobToPublicKeyToken
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e2459b4f91e7e189990b65fa4d7ca860ff73c51
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741323"
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="683da-102">\_Функция AxlPublicKeyBlobToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="683da-102">\_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="683da-103">Вычисляет токен открытого ключа строгого имени из формата CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="683da-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="683da-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="683da-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="683da-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="683da-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="683da-106">[в] Большой двоичный объект открытого ключа CSP.</span><span class="sxs-lookup"><span data-stu-id="683da-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="683da-107">[из] Указатель на WCHAR \* для получения шестнадцатеричного кодированного хэша открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="683da-107">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="683da-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="683da-108">Return Value</span></span>  
 <span data-ttu-id="683da-109">`S_OK`, если функция выполняется успешно. В противном случае — `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="683da-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="683da-110">См. также</span><span class="sxs-lookup"><span data-stu-id="683da-110">See also</span></span>

- [<span data-ttu-id="683da-111">Authenticode</span><span class="sxs-lookup"><span data-stu-id="683da-111">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
