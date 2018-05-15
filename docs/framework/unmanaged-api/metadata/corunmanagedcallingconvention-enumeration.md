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
ms.openlocfilehash: 0b249d26335a66b55d0643f3e75bfd90554f731e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="2b08d-102">Перечисление CorUnmanagedCallingConvention</span><span class="sxs-lookup"><span data-stu-id="2b08d-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="2b08d-103">Задает соглашение о вызовах для неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="2b08d-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b08d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b08d-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="2b08d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2b08d-105">Members</span></span>  
  
|<span data-ttu-id="2b08d-106">Член</span><span class="sxs-lookup"><span data-stu-id="2b08d-106">Member</span></span>|<span data-ttu-id="2b08d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2b08d-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="2b08d-108">C языка соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="2b08d-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="2b08d-109">Стандартное соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="2b08d-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="2b08d-110">«This» соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="2b08d-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="2b08d-111">«Быстрый» соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="2b08d-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="2b08d-112">Не используется.</span><span class="sxs-lookup"><span data-stu-id="2b08d-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="2b08d-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="2b08d-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="2b08d-114">Не используется.</span><span class="sxs-lookup"><span data-stu-id="2b08d-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="2b08d-115">Не используется.</span><span class="sxs-lookup"><span data-stu-id="2b08d-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b08d-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="2b08d-116">Remarks</span></span>  
 <span data-ttu-id="2b08d-117">Среда CLR не поддерживает «быстрый» соглашение о вызовах в .NET Framework версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="2b08d-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b08d-118">Требования</span><span class="sxs-lookup"><span data-stu-id="2b08d-118">Requirements</span></span>  
 <span data-ttu-id="2b08d-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b08d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b08d-120">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="2b08d-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2b08d-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b08d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b08d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2b08d-122">See Also</span></span>  
 [<span data-ttu-id="2b08d-123">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="2b08d-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
