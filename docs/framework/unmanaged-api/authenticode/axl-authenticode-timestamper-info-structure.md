---
title: Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9eef89c9e560da65d670ffe59649b44a64f8da6a
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039607"
---
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="13489-102">Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO</span><span class="sxs-lookup"><span data-stu-id="13489-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="13489-103">Определяет информацию об отметке времени Authenticode.</span><span class="sxs-lookup"><span data-stu-id="13489-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13489-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13489-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="13489-105">Участники</span><span class="sxs-lookup"><span data-stu-id="13489-105">Members</span></span>  
  
|<span data-ttu-id="13489-106">Член</span><span class="sxs-lookup"><span data-stu-id="13489-106">Member</span></span>|<span data-ttu-id="13489-107">Описание</span><span class="sxs-lookup"><span data-stu-id="13489-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="13489-108">Размер этой структуры.</span><span class="sxs-lookup"><span data-stu-id="13489-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="13489-109">Код ошибки.</span><span class="sxs-lookup"><span data-stu-id="13489-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="13489-110">Хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="13489-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="13489-111">Время отметки времени.</span><span class="sxs-lookup"><span data-stu-id="13489-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="13489-112">Контекст цепочки отметки времени.</span><span class="sxs-lookup"><span data-stu-id="13489-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="13489-113">См. структуру [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .</span><span class="sxs-lookup"><span data-stu-id="13489-113">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13489-114">См. также</span><span class="sxs-lookup"><span data-stu-id="13489-114">See also</span></span>

- [<span data-ttu-id="13489-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="13489-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
