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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097825"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="ca4f9-102">Перечисление CorEventAttr</span><span class="sxs-lookup"><span data-stu-id="ca4f9-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="ca4f9-103">Содержит значения, описывающие метаданные события.</span><span class="sxs-lookup"><span data-stu-id="ca4f9-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca4f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca4f9-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="ca4f9-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ca4f9-105">Members</span></span>  
  
|<span data-ttu-id="ca4f9-106">Член</span><span class="sxs-lookup"><span data-stu-id="ca4f9-106">Member</span></span>|<span data-ttu-id="ca4f9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ca4f9-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="ca4f9-108">Указывает, что событие является специальным, и указывает его имя как.</span><span class="sxs-lookup"><span data-stu-id="ca4f9-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="ca4f9-109">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="ca4f9-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="ca4f9-110">Указывает, что среда CLR должна проверять кодировку имени события.</span><span class="sxs-lookup"><span data-stu-id="ca4f9-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca4f9-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ca4f9-111">Requirements</span></span>  
 <span data-ttu-id="ca4f9-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca4f9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca4f9-113">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ca4f9-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ca4f9-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca4f9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca4f9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ca4f9-115">See also</span></span>

- [<span data-ttu-id="ca4f9-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="ca4f9-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
