---
title: Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
ms.openlocfilehash: 036397928703aea6199a59ae9c1e66153c30ec7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132495"
---
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="4cd47-102">Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO</span><span class="sxs-lookup"><span data-stu-id="4cd47-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="4cd47-103">Определяет информацию об отметке времени Authenticode.</span><span class="sxs-lookup"><span data-stu-id="4cd47-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cd47-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4cd47-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="4cd47-105">Члены</span><span class="sxs-lookup"><span data-stu-id="4cd47-105">Members</span></span>  
  
|<span data-ttu-id="4cd47-106">Член</span><span class="sxs-lookup"><span data-stu-id="4cd47-106">Member</span></span>|<span data-ttu-id="4cd47-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4cd47-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="4cd47-108">Размер этой структуры.</span><span class="sxs-lookup"><span data-stu-id="4cd47-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="4cd47-109">Код ошибки.</span><span class="sxs-lookup"><span data-stu-id="4cd47-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="4cd47-110">Хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="4cd47-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="4cd47-111">Время отметки времени.</span><span class="sxs-lookup"><span data-stu-id="4cd47-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="4cd47-112">Контекст цепочки отметки времени.</span><span class="sxs-lookup"><span data-stu-id="4cd47-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="4cd47-113">См. структуру [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .</span><span class="sxs-lookup"><span data-stu-id="4cd47-113">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4cd47-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4cd47-114">See also</span></span>

- [<span data-ttu-id="4cd47-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="4cd47-115">Authenticode</span></span>](index.md)
