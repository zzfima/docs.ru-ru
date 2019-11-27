---
title: Перечисление CorNotificationForTokenMovement
ms.date: 03/30/2017
api_name:
- CorNotificationForTokenMovement
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNotificationForTokenMovement
helpviewer_keywords:
- CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type:
- apiref
ms.openlocfilehash: 411fad0accb59431f776c5bd66e8bd3027ddd907
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450156"
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="b5adb-102">Перечисление CorNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="b5adb-102">CorNotificationForTokenMovement Enumeration</span></span>
<span data-ttu-id="b5adb-103">Указывает уведомления, которые будут отправляться клиенту API метаданных при выполнении сопоставления маркеров.</span><span class="sxs-lookup"><span data-stu-id="b5adb-103">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5adb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5adb-104">Syntax</span></span>  
  
```cpp  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a><span data-ttu-id="b5adb-105">Члены</span><span class="sxs-lookup"><span data-stu-id="b5adb-105">Members</span></span>  
  
|<span data-ttu-id="b5adb-106">Член</span><span class="sxs-lookup"><span data-stu-id="b5adb-106">Member</span></span>|<span data-ttu-id="b5adb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b5adb-107">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="b5adb-108">Уведомлять при перемещении маркеров `mdTypeRef`, `mdMethodDef`, `mdMemberRef`или `mdFieldDef`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-108">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="b5adb-109">Уведомлять при перемещении токена.</span><span class="sxs-lookup"><span data-stu-id="b5adb-109">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="b5adb-110">Не уведомлять при перемещении токенов.</span><span class="sxs-lookup"><span data-stu-id="b5adb-110">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="b5adb-111">Уведомлять при перемещении маркера `mdMethodDef`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-111">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="b5adb-112">Уведомлять при перемещении маркера `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-112">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="b5adb-113">Уведомлять при перемещении маркера `mdFieldDef`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-113">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="b5adb-114">Уведомлять при перемещении маркера `mdTypeRef`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-114">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="b5adb-115">Уведомлять при перемещении маркера `mdTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-115">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="b5adb-116">Уведомлять при перемещении маркера `mdParamDef`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-116">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="b5adb-117">Уведомлять при перемещении маркера `mdInterfaceImpl`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-117">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="b5adb-118">Уведомлять при перемещении маркера `mdProperty`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-118">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="b5adb-119">Уведомлять при перемещении маркера `mdEvent`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-119">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="b5adb-120">Уведомлять при перемещении маркера `mdSignature`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-120">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="b5adb-121">Уведомлять при перемещении маркера `mdTypeSpec`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-121">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="b5adb-122">Уведомлять при перемещении маркера `mdCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-122">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="b5adb-123">Уведомлять при перемещении маркера `mdSecurityValue`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-123">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="b5adb-124">Уведомлять при перемещении маркера `mdPermission`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-124">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="b5adb-125">Уведомлять при перемещении маркера `mdModuleRef`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-125">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="b5adb-126">Уведомлять при перемещении маркера `mdNameSpace`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-126">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="b5adb-127">Уведомлять при перемещении маркера `mdAssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-127">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="b5adb-128">Уведомлять при перемещении маркера `mdFile`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-128">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="b5adb-129">Уведомлять при перемещении маркера `mdExportedType`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-129">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="b5adb-130">Уведомлять при перемещении маркера `mdManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="b5adb-130">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5adb-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="b5adb-131">Remarks</span></span>  
 <span data-ttu-id="b5adb-132">Маркер может быть повторно сопоставлен (т. е. перемещен) во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="b5adb-132">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5adb-133">Требования</span><span class="sxs-lookup"><span data-stu-id="b5adb-133">Requirements</span></span>  
 <span data-ttu-id="b5adb-134">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5adb-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5adb-135">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="b5adb-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b5adb-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5adb-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5adb-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="b5adb-137">See also</span></span>

- [<span data-ttu-id="b5adb-138">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="b5adb-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
