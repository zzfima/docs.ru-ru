---
title: Функция CertFreeAuthenticodeSignerInfo
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 357a2ca0ffc733adb14a21624cbe28fb754c8240
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776727"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="99ba7-102">Функция CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="99ba7-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="99ba7-103">Освобождает ресурсы, выделенные для структуры [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="99ba7-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99ba7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99ba7-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99ba7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="99ba7-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="99ba7-106">[в, из] Информация о подписавшем, которую необходимо указывать.</span><span class="sxs-lookup"><span data-stu-id="99ba7-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="99ba7-107">См. структуру [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="99ba7-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99ba7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="99ba7-108">Return Value</span></span>  
 <span data-ttu-id="99ba7-109">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="99ba7-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="99ba7-110">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="99ba7-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ba7-111">См. также</span><span class="sxs-lookup"><span data-stu-id="99ba7-111">See also</span></span>

- [<span data-ttu-id="99ba7-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="99ba7-112">Authenticode</span></span>](index.md)
