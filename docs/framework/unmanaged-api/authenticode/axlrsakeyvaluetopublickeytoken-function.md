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
ms.openlocfilehash: 7ef73f0f7599fdff887437756a5995591fd8ec89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402416"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="83cec-102">Функция _AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="83cec-102">_AxlRSAKeyValueToPublicKeyToken Function</span></span>
<span data-ttu-id="83cec-103">Преобразует модули и экспоненту в строгое имя маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="83cec-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83cec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83cec-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83cec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="83cec-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="83cec-106">[in] Большой двоичный объект модуля кодировке base64 (от \<Modulus > элемент).</span><span class="sxs-lookup"><span data-stu-id="83cec-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="83cec-107">В разделе [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="83cec-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="83cec-108">[in] Большой двоичный объект экспоненты кодировке base64 (от \<показатель степени > элемент).</span><span class="sxs-lookup"><span data-stu-id="83cec-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="83cec-109">В разделе [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="83cec-109">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="83cec-110">[из] Указатель на WCHAR \* для получения шестнадцатеричного кодированного маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="83cec-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83cec-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="83cec-111">Return Value</span></span>  
 <span data-ttu-id="83cec-112">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="83cec-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="83cec-113">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="83cec-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83cec-114">См. также</span><span class="sxs-lookup"><span data-stu-id="83cec-114">See Also</span></span>  
 [<span data-ttu-id="83cec-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="83cec-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
