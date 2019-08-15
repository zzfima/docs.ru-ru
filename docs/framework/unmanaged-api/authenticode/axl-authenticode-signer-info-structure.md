---
title: Структура AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c69be0de98e2996176e7360bae0bb0736c1a797
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038445"
---
# <a name="axl_authenticode_signer_info-structure"></a><span data-ttu-id="3a7aa-102">Структура AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="3a7aa-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="3a7aa-103">Определяет информацию о подписавшем Authenticode.</span><span class="sxs-lookup"><span data-stu-id="3a7aa-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a7aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a7aa-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="3a7aa-105">Участники</span><span class="sxs-lookup"><span data-stu-id="3a7aa-105">Members</span></span>  
  
|<span data-ttu-id="3a7aa-106">Член</span><span class="sxs-lookup"><span data-stu-id="3a7aa-106">Member</span></span>|<span data-ttu-id="3a7aa-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3a7aa-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="3a7aa-108">Размер этой структуры.</span><span class="sxs-lookup"><span data-stu-id="3a7aa-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="3a7aa-109">Код ошибки.</span><span class="sxs-lookup"><span data-stu-id="3a7aa-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="3a7aa-110">Хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="3a7aa-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="3a7aa-111">Хэш.</span><span class="sxs-lookup"><span data-stu-id="3a7aa-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="3a7aa-112">Описание.</span><span class="sxs-lookup"><span data-stu-id="3a7aa-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="3a7aa-113">URL-адрес описания.</span><span class="sxs-lookup"><span data-stu-id="3a7aa-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="3a7aa-114">Контекст цепочки подписавшего.</span><span class="sxs-lookup"><span data-stu-id="3a7aa-114">The chain context of the signer.</span></span> <span data-ttu-id="3a7aa-115">См. структуру [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .</span><span class="sxs-lookup"><span data-stu-id="3a7aa-115">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a7aa-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3a7aa-116">See also</span></span>

- [<span data-ttu-id="3a7aa-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="3a7aa-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
