---
title: _AxlRSAKeyValueToPublicKeyToken function
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
ms.openlocfilehash: 49476a4417e5431842f8e2ba0371c53c5c9f03e9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207829"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="e70f8-102">\_Функция AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="e70f8-102">\_AxlRSAKeyValueToPublicKeyToken function</span></span>

<span data-ttu-id="e70f8-103">Преобразует модули и экспоненту в строгое имя маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="e70f8-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e70f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e70f8-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e70f8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e70f8-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="e70f8-106">[in] Большой двоичный объект модуля кодировке base64 (от \<Modulus > элемент).</span><span class="sxs-lookup"><span data-stu-id="e70f8-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="e70f8-107">См. в разделе [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) структуры.</span><span class="sxs-lookup"><span data-stu-id="e70f8-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="e70f8-108">[in] Большой двоичный объект экспоненты с кодировкой base64 (от \<Exponent > элемент).</span><span class="sxs-lookup"><span data-stu-id="e70f8-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="e70f8-109">См. в разделе [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) структуры.</span><span class="sxs-lookup"><span data-stu-id="e70f8-109">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="e70f8-110">[из] Указатель на WCHAR \* для получения шестнадцатеричного кодированного маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="e70f8-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e70f8-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e70f8-111">Return Value</span></span>  
 <span data-ttu-id="e70f8-112">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="e70f8-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="e70f8-113">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="e70f8-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e70f8-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e70f8-114">See also</span></span>

- [<span data-ttu-id="e70f8-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="e70f8-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
