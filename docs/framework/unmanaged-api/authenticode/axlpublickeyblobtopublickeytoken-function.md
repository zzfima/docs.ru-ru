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
ms.openlocfilehash: 33b8f47813a3bf43bd69741c9febb150fa3a92e3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099896"
---
# <a name="_axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="ffde1-102">\_функция Акслпубликкэйблобтопубликкэйтокен</span><span class="sxs-lookup"><span data-stu-id="ffde1-102">\_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="ffde1-103">Вычисляет токен открытого ключа строгого имени из формата CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="ffde1-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffde1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffde1-104">Syntax</span></span>  
  
```cpp  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffde1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ffde1-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="ffde1-106">[в] Большой двоичный объект открытого ключа CSP.</span><span class="sxs-lookup"><span data-stu-id="ffde1-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="ffde1-107">[из] Указатель на WCHAR \* для получения шестнадцатеричного кодированного хэша открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="ffde1-107">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ffde1-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ffde1-108">Return Value</span></span>  
 <span data-ttu-id="ffde1-109">`S_OK`, если функция выполняется успешно. В противном случае — `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="ffde1-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffde1-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ffde1-110">See also</span></span>

- [<span data-ttu-id="ffde1-111">Authenticode</span><span class="sxs-lookup"><span data-stu-id="ffde1-111">Authenticode</span></span>](index.md)
