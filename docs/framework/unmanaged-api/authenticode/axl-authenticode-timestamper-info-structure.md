---
title: Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8060e95f06fd53ca985f84666cc81cfe49394fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659661"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="284fe-102">Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO</span><span class="sxs-lookup"><span data-stu-id="284fe-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="284fe-103">Определяет информацию об отметке времени Authenticode.</span><span class="sxs-lookup"><span data-stu-id="284fe-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="284fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="284fe-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="284fe-105">Участники</span><span class="sxs-lookup"><span data-stu-id="284fe-105">Members</span></span>  
  
|<span data-ttu-id="284fe-106">Член</span><span class="sxs-lookup"><span data-stu-id="284fe-106">Member</span></span>|<span data-ttu-id="284fe-107">Описание</span><span class="sxs-lookup"><span data-stu-id="284fe-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="284fe-108">Размер этой структуры.</span><span class="sxs-lookup"><span data-stu-id="284fe-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="284fe-109">Код ошибки.</span><span class="sxs-lookup"><span data-stu-id="284fe-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="284fe-110">Хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="284fe-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="284fe-111">Время отметки времени.</span><span class="sxs-lookup"><span data-stu-id="284fe-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="284fe-112">Контекст цепочки отметки времени.</span><span class="sxs-lookup"><span data-stu-id="284fe-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="284fe-113">См. в разделе [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) структуры.</span><span class="sxs-lookup"><span data-stu-id="284fe-113">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="284fe-114">См. также</span><span class="sxs-lookup"><span data-stu-id="284fe-114">See also</span></span>
- [<span data-ttu-id="284fe-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="284fe-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
