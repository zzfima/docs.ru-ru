---
title: Структура AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 024837870aade6b0beb76fe758a571b15fd14d59
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107670"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="e4d7e-102">Структура AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="e4d7e-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="e4d7e-103">Определяет информацию о подписавшем Authenticode.</span><span class="sxs-lookup"><span data-stu-id="e4d7e-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4d7e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4d7e-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e4d7e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="e4d7e-105">Members</span></span>  
  
|<span data-ttu-id="e4d7e-106">Член</span><span class="sxs-lookup"><span data-stu-id="e4d7e-106">Member</span></span>|<span data-ttu-id="e4d7e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e4d7e-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="e4d7e-108">Размер этой структуры.</span><span class="sxs-lookup"><span data-stu-id="e4d7e-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="e4d7e-109">Код ошибки.</span><span class="sxs-lookup"><span data-stu-id="e4d7e-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="e4d7e-110">Хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="e4d7e-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="e4d7e-111">Хэш.</span><span class="sxs-lookup"><span data-stu-id="e4d7e-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="e4d7e-112">Описание.</span><span class="sxs-lookup"><span data-stu-id="e4d7e-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="e4d7e-113">URL-адрес описания.</span><span class="sxs-lookup"><span data-stu-id="e4d7e-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="e4d7e-114">Контекст цепочки подписавшего.</span><span class="sxs-lookup"><span data-stu-id="e4d7e-114">The chain context of the signer.</span></span> <span data-ttu-id="e4d7e-115">См. в разделе [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) структуры.</span><span class="sxs-lookup"><span data-stu-id="e4d7e-115">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4d7e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e4d7e-116">See also</span></span>

- [<span data-ttu-id="e4d7e-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="e4d7e-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
