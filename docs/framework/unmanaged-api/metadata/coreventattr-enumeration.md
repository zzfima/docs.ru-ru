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
ms.openlocfilehash: ec2972605c40f4ba292f5a5f58d6d3efed53f966
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443557"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="9efec-102">Перечисление CorEventAttr</span><span class="sxs-lookup"><span data-stu-id="9efec-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="9efec-103">Содержит значения, описывающие метаданные события.</span><span class="sxs-lookup"><span data-stu-id="9efec-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9efec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9efec-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="9efec-105">Члены</span><span class="sxs-lookup"><span data-stu-id="9efec-105">Members</span></span>  
  
|<span data-ttu-id="9efec-106">Член</span><span class="sxs-lookup"><span data-stu-id="9efec-106">Member</span></span>|<span data-ttu-id="9efec-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9efec-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="9efec-108">Указывает, что событие является специальным, и что его имя описывает, как это делать.</span><span class="sxs-lookup"><span data-stu-id="9efec-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="9efec-109">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9efec-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="9efec-110">Указывает, что среда CLR должна проверять кодировку имени события.</span><span class="sxs-lookup"><span data-stu-id="9efec-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9efec-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9efec-111">Requirements</span></span>  
 <span data-ttu-id="9efec-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9efec-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9efec-113">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="9efec-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9efec-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9efec-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efec-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9efec-115">See also</span></span>

- [<span data-ttu-id="9efec-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="9efec-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
