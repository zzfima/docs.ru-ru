---
title: Структура AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd07707b5a80ec0980fc50b27caddf0a24398fd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400449"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="e9953-102">Структура AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="e9953-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="e9953-103">Определяет информацию о подписавшем Authenticode.</span><span class="sxs-lookup"><span data-stu-id="e9953-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9953-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9953-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e9953-105">Участники</span><span class="sxs-lookup"><span data-stu-id="e9953-105">Members</span></span>  
  
|<span data-ttu-id="e9953-106">Член</span><span class="sxs-lookup"><span data-stu-id="e9953-106">Member</span></span>|<span data-ttu-id="e9953-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e9953-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="e9953-108">Размер этой структуры.</span><span class="sxs-lookup"><span data-stu-id="e9953-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="e9953-109">Код ошибки.</span><span class="sxs-lookup"><span data-stu-id="e9953-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="e9953-110">Хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="e9953-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="e9953-111">Хэш.</span><span class="sxs-lookup"><span data-stu-id="e9953-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="e9953-112">Описание.</span><span class="sxs-lookup"><span data-stu-id="e9953-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="e9953-113">URL-адрес описания.</span><span class="sxs-lookup"><span data-stu-id="e9953-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="e9953-114">Контекст цепочки подписавшего.</span><span class="sxs-lookup"><span data-stu-id="e9953-114">The chain context of the signer.</span></span> <span data-ttu-id="e9953-115">В разделе [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="e9953-115">See the [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9953-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e9953-116">See Also</span></span>  
 [<span data-ttu-id="e9953-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="e9953-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
