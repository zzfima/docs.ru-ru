---
title: Структура AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 024837870aade6b0beb76fe758a571b15fd14d59
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107670"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="bd697-102">Структура AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="bd697-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="bd697-103">Определяет информацию о подписавшем Authenticode.</span><span class="sxs-lookup"><span data-stu-id="bd697-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd697-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd697-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="bd697-105">Участники</span><span class="sxs-lookup"><span data-stu-id="bd697-105">Members</span></span>  
  
|<span data-ttu-id="bd697-106">Член</span><span class="sxs-lookup"><span data-stu-id="bd697-106">Member</span></span>|<span data-ttu-id="bd697-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bd697-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="bd697-108">Размер этой структуры.</span><span class="sxs-lookup"><span data-stu-id="bd697-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="bd697-109">Код ошибки.</span><span class="sxs-lookup"><span data-stu-id="bd697-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="bd697-110">Хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="bd697-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="bd697-111">Хэш.</span><span class="sxs-lookup"><span data-stu-id="bd697-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="bd697-112">Описание.</span><span class="sxs-lookup"><span data-stu-id="bd697-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="bd697-113">URL-адрес описания.</span><span class="sxs-lookup"><span data-stu-id="bd697-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="bd697-114">Контекст цепочки подписавшего.</span><span class="sxs-lookup"><span data-stu-id="bd697-114">The chain context of the signer.</span></span> <span data-ttu-id="bd697-115">См. в разделе [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) структуры.</span><span class="sxs-lookup"><span data-stu-id="bd697-115">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd697-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bd697-116">See also</span></span>

- [<span data-ttu-id="bd697-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="bd697-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
