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
ms.openlocfilehash: 2796be32154275387da891683cc5053095f534af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772325"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="7b2d9-102">Перечисление CorSetENC</span><span class="sxs-lookup"><span data-stu-id="7b2d9-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="7b2d9-103">Содержит значения, используемые для оказания влияния на поведение во время создания метаданных.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b2d9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b2d9-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="7b2d9-105">Участники</span><span class="sxs-lookup"><span data-stu-id="7b2d9-105">Members</span></span>  
  
|<span data-ttu-id="7b2d9-106">Член</span><span class="sxs-lookup"><span data-stu-id="7b2d9-106">Member</span></span>|<span data-ttu-id="7b2d9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7b2d9-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="7b2d9-108">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="7b2d9-109">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="7b2d9-110">Указывает, что в то время как метаданные могут быть обновлены, невозможно переместить маркеры.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="7b2d9-111">Указывает, что маркеры можно переместить во время обновления.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="7b2d9-112">Указывает, что обновления могут состоять только из добавлений.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="7b2d9-113">Маркеры не могут быть перемещены.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="7b2d9-114">Указывает добавочной компиляции.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="7b2d9-115">Указывает, что только измененные метаданные должны сохраняться.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="7b2d9-116">Включает в себя `MDUpdateENC`, `MDUpdateFull` и `MDUpdateIncremental`.</span><span class="sxs-lookup"><span data-stu-id="7b2d9-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7b2d9-117">Требования</span><span class="sxs-lookup"><span data-stu-id="7b2d9-117">Requirements</span></span>  
 <span data-ttu-id="7b2d9-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b2d9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b2d9-119">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7b2d9-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7b2d9-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b2d9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b2d9-121">См. также</span><span class="sxs-lookup"><span data-stu-id="7b2d9-121">See also</span></span>

- [<span data-ttu-id="7b2d9-122">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="7b2d9-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
