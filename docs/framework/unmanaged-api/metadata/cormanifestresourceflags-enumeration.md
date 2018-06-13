---
title: Перечисление CorManifestResourceFlags
ms.date: 03/30/2017
api_name:
- CorManifestResourceFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorManifestResourceFlags
helpviewer_keywords:
- CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21cce26c94d26f6c079fca644a31bf83cd1a6432
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440714"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="afb31-102">Перечисление CorManifestResourceFlags</span><span class="sxs-lookup"><span data-stu-id="afb31-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="afb31-103">Задает видимость ресурсов, зашифрованных в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="afb31-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afb31-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="afb31-104">Syntax</span></span>  
  
```  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="afb31-105">Участники</span><span class="sxs-lookup"><span data-stu-id="afb31-105">Members</span></span>  
  
|<span data-ttu-id="afb31-106">Член</span><span class="sxs-lookup"><span data-stu-id="afb31-106">Member</span></span>|<span data-ttu-id="afb31-107">Описание</span><span class="sxs-lookup"><span data-stu-id="afb31-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="afb31-108">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="afb31-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="afb31-109">Ресурсы являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="afb31-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="afb31-110">Ресурсы являются закрытыми.</span><span class="sxs-lookup"><span data-stu-id="afb31-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="afb31-111">Требования</span><span class="sxs-lookup"><span data-stu-id="afb31-111">Requirements</span></span>  
 <span data-ttu-id="afb31-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afb31-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afb31-113">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="afb31-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="afb31-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afb31-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb31-115">См. также</span><span class="sxs-lookup"><span data-stu-id="afb31-115">See Also</span></span>  
 [<span data-ttu-id="afb31-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="afb31-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
