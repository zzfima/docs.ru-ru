---
title: Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7f4fff4f2c2b3dd04625f4cf50b8b19a0ef6f39
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "43254663"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="74401-102">Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO</span><span class="sxs-lookup"><span data-stu-id="74401-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="74401-103">Определяет информацию об отметке времени Authenticode.</span><span class="sxs-lookup"><span data-stu-id="74401-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74401-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74401-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="74401-105">Участники</span><span class="sxs-lookup"><span data-stu-id="74401-105">Members</span></span>  
  
|<span data-ttu-id="74401-106">Член</span><span class="sxs-lookup"><span data-stu-id="74401-106">Member</span></span>|<span data-ttu-id="74401-107">Описание</span><span class="sxs-lookup"><span data-stu-id="74401-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="74401-108">Размер этой структуры.</span><span class="sxs-lookup"><span data-stu-id="74401-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="74401-109">Код ошибки.</span><span class="sxs-lookup"><span data-stu-id="74401-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="74401-110">Хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="74401-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="74401-111">Время отметки времени.</span><span class="sxs-lookup"><span data-stu-id="74401-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="74401-112">Контекст цепочки отметки времени.</span><span class="sxs-lookup"><span data-stu-id="74401-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="74401-113">См. в разделе [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) структуры.</span><span class="sxs-lookup"><span data-stu-id="74401-113">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74401-114">См. также</span><span class="sxs-lookup"><span data-stu-id="74401-114">See Also</span></span>  
 [<span data-ttu-id="74401-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="74401-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
