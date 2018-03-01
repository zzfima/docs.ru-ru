---
title: "Перечисление CorSetENC"
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
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0f39a1481361377fce3f6b55cf6c7daf8c075ce5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="7b12d-102">Перечисление CorSetENC</span><span class="sxs-lookup"><span data-stu-id="7b12d-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="7b12d-103">Содержит значения, используемые для оказания влияния на поведение во время создания метаданных.</span><span class="sxs-lookup"><span data-stu-id="7b12d-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b12d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b12d-104">Syntax</span></span>  
  
```  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a><span data-ttu-id="7b12d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="7b12d-105">Members</span></span>  
  
|<span data-ttu-id="7b12d-106">Член</span><span class="sxs-lookup"><span data-stu-id="7b12d-106">Member</span></span>|<span data-ttu-id="7b12d-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="7b12d-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="7b12d-108">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="7b12d-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="7b12d-109">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="7b12d-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="7b12d-110">Указывает, тогда как метаданные могут быть обновлены, маркеров не может быть перемещен.</span><span class="sxs-lookup"><span data-stu-id="7b12d-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="7b12d-111">Указывает, что токены можно переместить, во время обновления.</span><span class="sxs-lookup"><span data-stu-id="7b12d-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="7b12d-112">Указывает, что обновления могут состоять только из добавлений.</span><span class="sxs-lookup"><span data-stu-id="7b12d-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="7b12d-113">Маркеры не могут быть перемещены.</span><span class="sxs-lookup"><span data-stu-id="7b12d-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="7b12d-114">Указывает добавочной компиляции.</span><span class="sxs-lookup"><span data-stu-id="7b12d-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="7b12d-115">Указывает, что только измененные метаданные должны сохраняться.</span><span class="sxs-lookup"><span data-stu-id="7b12d-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="7b12d-116">Включает в себя `MDUpdateENC`, `MDUpdateFull` и `MDUpdateIncremental`.</span><span class="sxs-lookup"><span data-stu-id="7b12d-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7b12d-117">Требования</span><span class="sxs-lookup"><span data-stu-id="7b12d-117">Requirements</span></span>  
 <span data-ttu-id="7b12d-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b12d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b12d-119">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7b12d-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7b12d-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b12d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b12d-121">См. также</span><span class="sxs-lookup"><span data-stu-id="7b12d-121">See Also</span></span>  
 [<span data-ttu-id="7b12d-122">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="7b12d-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
