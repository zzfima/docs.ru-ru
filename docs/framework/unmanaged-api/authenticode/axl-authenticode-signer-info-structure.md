---
title: Структура AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b9f54c7c57d122ac1214b9f31cc4e1d1cddd71c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392183"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="e0bd0-102">Структура AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="e0bd0-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="e0bd0-103">Определяет информацию о подписавшем Authenticode.</span><span class="sxs-lookup"><span data-stu-id="e0bd0-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0bd0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0bd0-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="e0bd0-105">Участники</span><span class="sxs-lookup"><span data-stu-id="e0bd0-105">Members</span></span>  
  
|<span data-ttu-id="e0bd0-106">Член</span><span class="sxs-lookup"><span data-stu-id="e0bd0-106">Member</span></span>|<span data-ttu-id="e0bd0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e0bd0-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="e0bd0-108">Размер этой структуры.</span><span class="sxs-lookup"><span data-stu-id="e0bd0-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="e0bd0-109">Код ошибки.</span><span class="sxs-lookup"><span data-stu-id="e0bd0-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="e0bd0-110">Хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="e0bd0-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="e0bd0-111">Хэш.</span><span class="sxs-lookup"><span data-stu-id="e0bd0-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="e0bd0-112">Описание.</span><span class="sxs-lookup"><span data-stu-id="e0bd0-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="e0bd0-113">URL-адрес описания.</span><span class="sxs-lookup"><span data-stu-id="e0bd0-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="e0bd0-114">Контекст цепочки подписавшего.</span><span class="sxs-lookup"><span data-stu-id="e0bd0-114">The chain context of the signer.</span></span> <span data-ttu-id="e0bd0-115">См. в разделе [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) структуры.</span><span class="sxs-lookup"><span data-stu-id="e0bd0-115">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0bd0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e0bd0-116">See Also</span></span>  
 [<span data-ttu-id="e0bd0-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="e0bd0-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
