---
title: Функция _AxlRSAKeyValueToPublicKeyToken
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e09391af9b5d71cfa423b3bf1a2b307117d0dee1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385891"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="6368c-102">\_Функция AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="6368c-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="6368c-103">Преобразует модули и экспоненту в строгое имя маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="6368c-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6368c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6368c-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
### <a name="parameters"></a><span data-ttu-id="6368c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6368c-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="6368c-106">[in] Большой двоичный объект модуля кодировке base64 (от \<Modulus > элемент).</span><span class="sxs-lookup"><span data-stu-id="6368c-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="6368c-107">См. в разделе [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) структуры.</span><span class="sxs-lookup"><span data-stu-id="6368c-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="6368c-108">[in] Большой двоичный объект экспоненты с кодировкой base64 (от \<Exponent > элемент).</span><span class="sxs-lookup"><span data-stu-id="6368c-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="6368c-109">См. в разделе [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) структуры.</span><span class="sxs-lookup"><span data-stu-id="6368c-109">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="6368c-110">[из] Указатель на WCHAR \* для получения шестнадцатеричного кодированного маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="6368c-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6368c-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6368c-111">Return Value</span></span>  
 <span data-ttu-id="6368c-112">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="6368c-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="6368c-113">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="6368c-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6368c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6368c-114">See Also</span></span>  
 [<span data-ttu-id="6368c-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="6368c-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
