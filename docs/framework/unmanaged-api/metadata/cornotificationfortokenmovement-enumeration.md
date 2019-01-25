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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 745ba18fd1a36789f06bcd3dd4d183c9b28b9875
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650110"
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="2184a-102">Перечисление CorNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="2184a-102">CorNotificationForTokenMovement Enumeration</span></span>
<span data-ttu-id="2184a-103">Указывает уведомления, которые будут отправляться клиенту метаданных API, когда происходит новое сопоставление маркеров.</span><span class="sxs-lookup"><span data-stu-id="2184a-103">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2184a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2184a-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="2184a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2184a-105">Members</span></span>  
  
|<span data-ttu-id="2184a-106">Член</span><span class="sxs-lookup"><span data-stu-id="2184a-106">Member</span></span>|<span data-ttu-id="2184a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2184a-107">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="2184a-108">Отправить уведомление при `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, или `mdFieldDef` токенов перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-108">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="2184a-109">Уведомлять о перемещении маркера.</span><span class="sxs-lookup"><span data-stu-id="2184a-109">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="2184a-110">Не уведомлять о перемещении маркера.</span><span class="sxs-lookup"><span data-stu-id="2184a-110">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="2184a-111">Уведомлять, если `mdMethodDef` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-111">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="2184a-112">Уведомлять, если `mdMemberRef` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-112">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="2184a-113">Уведомлять, если `mdFieldDef` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-113">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="2184a-114">Уведомлять, если `mdTypeRef` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-114">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="2184a-115">Уведомлять, если `mdTypeDef` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-115">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="2184a-116">Уведомлять, если `mdParamDef` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-116">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="2184a-117">Уведомлять, если `mdInterfaceImpl` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-117">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="2184a-118">Уведомлять, если `mdProperty` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-118">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="2184a-119">Уведомлять, если `mdEvent` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-119">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="2184a-120">Уведомлять, если `mdSignature` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-120">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="2184a-121">Уведомлять, если `mdTypeSpec` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-121">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="2184a-122">Уведомлять, если `mdCustomAttribute` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-122">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="2184a-123">Уведомлять, если `mdSecurityValue` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-123">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="2184a-124">Уведомлять, если `mdPermission` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-124">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="2184a-125">Уведомлять, если `mdModuleRef` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-125">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="2184a-126">Уведомлять, если `mdNameSpace` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-126">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="2184a-127">Уведомлять, если `mdAssemblyRef` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-127">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="2184a-128">Уведомлять, если `mdFile` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-128">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="2184a-129">Уведомлять, если `mdExportedType` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-129">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="2184a-130">Уведомлять, если `mdManifestResource` маркер перемещения.</span><span class="sxs-lookup"><span data-stu-id="2184a-130">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2184a-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="2184a-131">Remarks</span></span>  
 <span data-ttu-id="2184a-132">Маркер может быть повторно сопоставлен (которые перемещаются) во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="2184a-132">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2184a-133">Требования</span><span class="sxs-lookup"><span data-stu-id="2184a-133">Requirements</span></span>  
 <span data-ttu-id="2184a-134">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2184a-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2184a-135">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="2184a-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2184a-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2184a-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2184a-137">См. также</span><span class="sxs-lookup"><span data-stu-id="2184a-137">See also</span></span>
- [<span data-ttu-id="2184a-138">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="2184a-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
