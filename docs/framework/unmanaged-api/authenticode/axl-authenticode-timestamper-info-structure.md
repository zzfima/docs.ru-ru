---
title: Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dce0e67479418cd8227c75fadd8872a41ae1a799
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741347"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="55943-102">Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO</span><span class="sxs-lookup"><span data-stu-id="55943-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="55943-103">Определяет информацию об отметке времени Authenticode.</span><span class="sxs-lookup"><span data-stu-id="55943-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55943-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55943-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="55943-105">Участники</span><span class="sxs-lookup"><span data-stu-id="55943-105">Members</span></span>  
  
|<span data-ttu-id="55943-106">Член</span><span class="sxs-lookup"><span data-stu-id="55943-106">Member</span></span>|<span data-ttu-id="55943-107">Описание</span><span class="sxs-lookup"><span data-stu-id="55943-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="55943-108">Размер этой структуры.</span><span class="sxs-lookup"><span data-stu-id="55943-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="55943-109">Код ошибки.</span><span class="sxs-lookup"><span data-stu-id="55943-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="55943-110">Хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="55943-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="55943-111">Время отметки времени.</span><span class="sxs-lookup"><span data-stu-id="55943-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="55943-112">Контекст цепочки отметки времени.</span><span class="sxs-lookup"><span data-stu-id="55943-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="55943-113">См. в разделе [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) структуры.</span><span class="sxs-lookup"><span data-stu-id="55943-113">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55943-114">См. также</span><span class="sxs-lookup"><span data-stu-id="55943-114">See also</span></span>

- [<span data-ttu-id="55943-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="55943-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
