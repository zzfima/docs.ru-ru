---
title: Перечисление CorUnmanagedCallingConvention
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff308a81282a1cc14c35583daf9cbb057149e556
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178455"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="67f69-102">Перечисление CorUnmanagedCallingConvention</span><span class="sxs-lookup"><span data-stu-id="67f69-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="67f69-103">Задает соглашения о вызовах для неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="67f69-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f69-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67f69-104">Syntax</span></span>  
  
```  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="67f69-105">Участники</span><span class="sxs-lookup"><span data-stu-id="67f69-105">Members</span></span>  
  
|<span data-ttu-id="67f69-106">Член</span><span class="sxs-lookup"><span data-stu-id="67f69-106">Member</span></span>|<span data-ttu-id="67f69-107">Описание</span><span class="sxs-lookup"><span data-stu-id="67f69-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="67f69-108">C языка соглашение о вызове.</span><span class="sxs-lookup"><span data-stu-id="67f69-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="67f69-109">Стандартный соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="67f69-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="67f69-110">«This» соглашение о вызове.</span><span class="sxs-lookup"><span data-stu-id="67f69-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="67f69-111">«Быстрый» о вызовах.</span><span class="sxs-lookup"><span data-stu-id="67f69-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="67f69-112">Не используется.</span><span class="sxs-lookup"><span data-stu-id="67f69-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="67f69-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="67f69-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="67f69-114">Не используется.</span><span class="sxs-lookup"><span data-stu-id="67f69-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="67f69-115">Не используется.</span><span class="sxs-lookup"><span data-stu-id="67f69-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67f69-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="67f69-116">Remarks</span></span>  
 <span data-ttu-id="67f69-117">Среда CLR не поддерживает «быстрый» соглашение о вызове в .NET Framework версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="67f69-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67f69-118">Требования</span><span class="sxs-lookup"><span data-stu-id="67f69-118">Requirements</span></span>  
 <span data-ttu-id="67f69-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67f69-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67f69-120">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="67f69-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="67f69-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67f69-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67f69-122">См. также</span><span class="sxs-lookup"><span data-stu-id="67f69-122">See also</span></span>

- [<span data-ttu-id="67f69-123">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="67f69-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
