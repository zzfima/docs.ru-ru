---
title: "Перечисление CorEventAttr"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorEventAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorEventAttr
helpviewer_keywords:
- CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c4302ff7627bf5e06f3c1b1263ec38a31393d411
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="1e868-102">Перечисление CorEventAttr</span><span class="sxs-lookup"><span data-stu-id="1e868-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="1e868-103">Содержит значения, описывающие метаданные события.</span><span class="sxs-lookup"><span data-stu-id="1e868-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e868-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e868-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="1e868-105">Участники</span><span class="sxs-lookup"><span data-stu-id="1e868-105">Members</span></span>  
  
|<span data-ttu-id="1e868-106">Член</span><span class="sxs-lookup"><span data-stu-id="1e868-106">Member</span></span>|<span data-ttu-id="1e868-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="1e868-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="1e868-108">Указывает, что событие является специальным и указывает его имя как.</span><span class="sxs-lookup"><span data-stu-id="1e868-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="1e868-109">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="1e868-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="1e868-110">Указывает, что общеязыковая среда выполнения должна проверять кодировку имени события.</span><span class="sxs-lookup"><span data-stu-id="1e868-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e868-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1e868-111">Requirements</span></span>  
 <span data-ttu-id="1e868-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e868-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e868-113">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="1e868-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1e868-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e868-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e868-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1e868-115">See Also</span></span>  
 [<span data-ttu-id="1e868-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="1e868-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
