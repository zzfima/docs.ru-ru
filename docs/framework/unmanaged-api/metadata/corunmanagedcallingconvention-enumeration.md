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
ms.openlocfilehash: 58d30e71929d314ee36adb9f83270858ff8a161b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442449"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="7dad5-102">Перечисление CorUnmanagedCallingConvention</span><span class="sxs-lookup"><span data-stu-id="7dad5-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="7dad5-103">Указывает соглашения о вызовах для неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="7dad5-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dad5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7dad5-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="7dad5-105">Члены</span><span class="sxs-lookup"><span data-stu-id="7dad5-105">Members</span></span>  
  
|<span data-ttu-id="7dad5-106">Член</span><span class="sxs-lookup"><span data-stu-id="7dad5-106">Member</span></span>|<span data-ttu-id="7dad5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7dad5-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="7dad5-108">Соглашение о вызовах языка C.</span><span class="sxs-lookup"><span data-stu-id="7dad5-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="7dad5-109">Стандартное соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="7dad5-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="7dad5-110">Соглашение о вызовах "this".</span><span class="sxs-lookup"><span data-stu-id="7dad5-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="7dad5-111">Соглашение о вызовах "Fast".</span><span class="sxs-lookup"><span data-stu-id="7dad5-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="7dad5-112">Не используется.</span><span class="sxs-lookup"><span data-stu-id="7dad5-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="7dad5-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="7dad5-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="7dad5-114">Не используется.</span><span class="sxs-lookup"><span data-stu-id="7dad5-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="7dad5-115">Не используется.</span><span class="sxs-lookup"><span data-stu-id="7dad5-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dad5-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="7dad5-116">Remarks</span></span>  
 <span data-ttu-id="7dad5-117">Среда CLR не поддерживает "быстрое" соглашение о вызовах в .NET Framework версии 1,0.</span><span class="sxs-lookup"><span data-stu-id="7dad5-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dad5-118">Требования</span><span class="sxs-lookup"><span data-stu-id="7dad5-118">Requirements</span></span>  
 <span data-ttu-id="7dad5-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dad5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dad5-120">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="7dad5-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7dad5-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dad5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dad5-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="7dad5-122">See also</span></span>

- [<span data-ttu-id="7dad5-123">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="7dad5-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
