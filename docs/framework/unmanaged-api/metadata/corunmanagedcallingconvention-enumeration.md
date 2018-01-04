---
title: "Перечисление CorUnmanagedCallingConvention"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorUnmanagedCallingConvention
api_location: mscoree.dll
api_type: COM
f1_keywords: CorUnmanagedCallingConvention
helpviewer_keywords: CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 446a948c8809d9f098ede8fbb9b426f6169ce812
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="0b45c-102">Перечисление CorUnmanagedCallingConvention</span><span class="sxs-lookup"><span data-stu-id="0b45c-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="0b45c-103">Задает соглашение о вызовах для неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="0b45c-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b45c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b45c-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0b45c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0b45c-105">Members</span></span>  
  
|<span data-ttu-id="0b45c-106">Член</span><span class="sxs-lookup"><span data-stu-id="0b45c-106">Member</span></span>|<span data-ttu-id="0b45c-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="0b45c-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="0b45c-108">C языка соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="0b45c-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="0b45c-109">Стандартное соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="0b45c-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="0b45c-110">«This» соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="0b45c-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="0b45c-111">«Быстрый» соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="0b45c-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="0b45c-112">Не используется.</span><span class="sxs-lookup"><span data-stu-id="0b45c-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="0b45c-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="0b45c-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="0b45c-114">Не используется.</span><span class="sxs-lookup"><span data-stu-id="0b45c-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="0b45c-115">Не используется.</span><span class="sxs-lookup"><span data-stu-id="0b45c-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b45c-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b45c-116">Remarks</span></span>  
 <span data-ttu-id="0b45c-117">Среда CLR не поддерживает «быстрый» соглашение о вызовах в .NET Framework версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="0b45c-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b45c-118">Требования</span><span class="sxs-lookup"><span data-stu-id="0b45c-118">Requirements</span></span>  
 <span data-ttu-id="0b45c-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b45c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b45c-120">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="0b45c-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0b45c-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b45c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b45c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0b45c-122">See Also</span></span>  
 [<span data-ttu-id="0b45c-123">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="0b45c-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
