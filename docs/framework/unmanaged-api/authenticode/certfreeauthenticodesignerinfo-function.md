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
ms.openlocfilehash: a233e0b8d17b9ee61b1991086f794c9fb20f89e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099833"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="76fd4-102">Функция CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="76fd4-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="76fd4-103">Освобождает ресурсы, выделенные для структуры [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="76fd4-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76fd4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76fd4-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76fd4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="76fd4-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="76fd4-106">[в, из] Информация о подписавшем, которую необходимо указывать.</span><span class="sxs-lookup"><span data-stu-id="76fd4-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="76fd4-107">См. структуру [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="76fd4-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76fd4-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="76fd4-108">Return Value</span></span>  
 <span data-ttu-id="76fd4-109">`S_OK`, если функция выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="76fd4-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="76fd4-110">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="76fd4-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76fd4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="76fd4-111">See also</span></span>

- [<span data-ttu-id="76fd4-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="76fd4-112">Authenticode</span></span>](index.md)
