---
title: Перечисление CorSetENC
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fd903cb4a9ce664b7a1c958a3fef0c639d6845d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122321"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="b0ba4-102">Перечисление CorSetENC</span><span class="sxs-lookup"><span data-stu-id="b0ba4-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="b0ba4-103">Содержит значения, используемые для оказания влияния на поведение во время создания метаданных.</span><span class="sxs-lookup"><span data-stu-id="b0ba4-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0ba4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0ba4-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b0ba4-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b0ba4-105">Members</span></span>  
  
|<span data-ttu-id="b0ba4-106">Член</span><span class="sxs-lookup"><span data-stu-id="b0ba4-106">Member</span></span>|<span data-ttu-id="b0ba4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b0ba4-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="b0ba4-108">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b0ba4-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="b0ba4-109">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b0ba4-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="b0ba4-110">Указывает, что в то время как метаданные могут быть обновлены, невозможно переместить маркеры.</span><span class="sxs-lookup"><span data-stu-id="b0ba4-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="b0ba4-111">Указывает, что маркеры можно переместить во время обновления.</span><span class="sxs-lookup"><span data-stu-id="b0ba4-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="b0ba4-112">Указывает, что обновления могут состоять только из добавлений.</span><span class="sxs-lookup"><span data-stu-id="b0ba4-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="b0ba4-113">Маркеры не могут быть перемещены.</span><span class="sxs-lookup"><span data-stu-id="b0ba4-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="b0ba4-114">Указывает добавочной компиляции.</span><span class="sxs-lookup"><span data-stu-id="b0ba4-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="b0ba4-115">Указывает, что только измененные метаданные должны сохраняться.</span><span class="sxs-lookup"><span data-stu-id="b0ba4-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="b0ba4-116">Включает в себя `MDUpdateENC`, `MDUpdateFull` и `MDUpdateIncremental`.</span><span class="sxs-lookup"><span data-stu-id="b0ba4-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0ba4-117">Требования</span><span class="sxs-lookup"><span data-stu-id="b0ba4-117">Requirements</span></span>  
 <span data-ttu-id="b0ba4-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0ba4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0ba4-119">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="b0ba4-119">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="b0ba4-120">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b0ba4-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b0ba4-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b0ba4-121">See also</span></span>

- [<span data-ttu-id="b0ba4-122">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="b0ba4-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
