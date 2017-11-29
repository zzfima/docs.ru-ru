---
title: "Функция _AxlRSAKeyValueToPublicKeyToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _AxlRSAKeyValueToPublicKeyToken
api_location: clr.dll
api_type: DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4af27a2abf1a0bcf4d79eda389c5f79f0ecb1eef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a><span data-ttu-id="73992-102">Функция _AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="73992-102">_AxlRSAKeyValueToPublicKeyToken Function</span></span>
<span data-ttu-id="73992-103">Преобразует модули и экспоненту в строгое имя маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="73992-103">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73992-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73992-104">Syntax</span></span>  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73992-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="73992-105">Parameters</span></span>  
 `pModulusBlob`  
 <span data-ttu-id="73992-106">[in] Большой двоичный объект модуля кодировке base64 (от \<Modulus > элемент).</span><span class="sxs-lookup"><span data-stu-id="73992-106">[in] The base64-encoded Modulus blob (from the \<Modulus> element).</span></span>  <span data-ttu-id="73992-107">В разделе [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="73992-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `pExponentBlob`  
 <span data-ttu-id="73992-108">[in] Большой двоичный объект экспоненты кодировке base64 (от \<показатель степени > элемент).</span><span class="sxs-lookup"><span data-stu-id="73992-108">[in] The base64-encoded Exponent blob (from the \<Exponent> element).</span></span> <span data-ttu-id="73992-109">В разделе [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="73992-109">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `ppwszPublicKeyToken`  
 <span data-ttu-id="73992-110">[из] Указатель на WCHAR * для получения шестнадцатеричного кодированного маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="73992-110">[out] A pointer to WCHAR * to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73992-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="73992-111">Return Value</span></span>  
 <span data-ttu-id="73992-112">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="73992-112">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="73992-113">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="73992-113">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73992-114">См. также</span><span class="sxs-lookup"><span data-stu-id="73992-114">See Also</span></span>  
 [<span data-ttu-id="73992-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="73992-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
