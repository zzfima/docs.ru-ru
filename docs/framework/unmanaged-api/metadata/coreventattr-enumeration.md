---
title: Перечисление CorEventAttr
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a1a50c15071ea1e696e508c779309225c7e7bfa2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097825"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="5e480-102">Перечисление CorEventAttr</span><span class="sxs-lookup"><span data-stu-id="5e480-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="5e480-103">Содержит значения, описывающие метаданные события.</span><span class="sxs-lookup"><span data-stu-id="5e480-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e480-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e480-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="5e480-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5e480-105">Members</span></span>  
  
|<span data-ttu-id="5e480-106">Член</span><span class="sxs-lookup"><span data-stu-id="5e480-106">Member</span></span>|<span data-ttu-id="5e480-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5e480-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="5e480-108">Указывает, что событие является специальным, и указывает его имя как.</span><span class="sxs-lookup"><span data-stu-id="5e480-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="5e480-109">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="5e480-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="5e480-110">Указывает, что среда CLR должна проверять кодировку имени события.</span><span class="sxs-lookup"><span data-stu-id="5e480-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e480-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5e480-111">Requirements</span></span>  
 <span data-ttu-id="5e480-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e480-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e480-113">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="5e480-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="5e480-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5e480-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5e480-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5e480-115">See also</span></span>

- [<span data-ttu-id="5e480-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="5e480-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
