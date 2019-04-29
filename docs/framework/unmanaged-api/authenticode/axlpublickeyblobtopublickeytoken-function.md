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
ms.openlocfilehash: 1b2535441da173ee13653c68f25039fd1431261a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948958"
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="411ad-102">Функция _AxlPublicKeyBlobToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="411ad-102">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="411ad-103">Вычисляет токен открытого ключа строгого имени из формата CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="411ad-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="411ad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="411ad-104">Syntax</span></span>  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="411ad-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="411ad-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="411ad-106">[в] Большой двоичный объект открытого ключа CSP.</span><span class="sxs-lookup"><span data-stu-id="411ad-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="411ad-107">[из] Указатель на WCHAR \* для получения шестнадцатеричного кодированного хэша открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="411ad-107">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="411ad-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="411ad-108">Return Value</span></span>  
 <span data-ttu-id="411ad-109">`S_OK`, если функция выполняется успешно. В противном случае — `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="411ad-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="411ad-110">См. также</span><span class="sxs-lookup"><span data-stu-id="411ad-110">See also</span></span>

- [<span data-ttu-id="411ad-111">Authenticode</span><span class="sxs-lookup"><span data-stu-id="411ad-111">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
