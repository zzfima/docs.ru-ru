---
title: "Функция _AxlRSAKeyValueToPublicKeyToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1380f658d9c154d9ea41228cace5f9a3eed39b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="365eb-102">Функция _AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="365eb-102">_AxlRSAKeyValueToPublicKeyToken Function</span></span>
<span data-ttu-id="365eb-103">Преобразует модули и экспоненту в строгое имя маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="365eb-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="365eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="365eb-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="365eb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="365eb-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="365eb-106">[in] Большой двоичный объект модуля кодировке base64 (от \<Modulus > элемент).</span><span class="sxs-lookup"><span data-stu-id="365eb-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="365eb-107">В разделе [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="365eb-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="365eb-108">[in] Большой двоичный объект экспоненты кодировке base64 (от \<показатель степени > элемент).</span><span class="sxs-lookup"><span data-stu-id="365eb-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="365eb-109">В разделе [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="365eb-109">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="365eb-110">[из] Указатель на WCHAR \* для получения шестнадцатеричного кодированного маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="365eb-110">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="365eb-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="365eb-111">Return Value</span></span>  
 <span data-ttu-id="365eb-112">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="365eb-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="365eb-113">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="365eb-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="365eb-114">См. также</span><span class="sxs-lookup"><span data-stu-id="365eb-114">See Also</span></span>  
 [<span data-ttu-id="365eb-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="365eb-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
