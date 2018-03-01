---
title: "Перечисление CorNotificationForTokenMovement"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e1d3ad11867dbd06dfe3f43cc31817a44cb96d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cornotificationfortokenmovement-enumeration"></a><span data-ttu-id="e870b-102">Перечисление CorNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="e870b-102">CorNotificationForTokenMovement Enumeration</span></span>
<span data-ttu-id="e870b-103">Указывает уведомления, которые будут отправлены клиенту API метаданных при возникновении маркера преобразования.</span><span class="sxs-lookup"><span data-stu-id="e870b-103">Specifies the notifications that will be sent to the metadata API client when a token remap occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e870b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e870b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e870b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="e870b-105">Members</span></span>  
  
|<span data-ttu-id="e870b-106">Член</span><span class="sxs-lookup"><span data-stu-id="e870b-106">Member</span></span>|<span data-ttu-id="e870b-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="e870b-107">Description</span></span>|  
|------------|-----------------|  
|`MDNotifyDefault`|<span data-ttu-id="e870b-108">Отправить уведомление при `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, или `mdFieldDef` маркеры перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-108">Notify when `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, or `mdFieldDef` tokens move.</span></span>|  
|`MDNotifyAll`|<span data-ttu-id="e870b-109">Уведомите о перемещении маркера.</span><span class="sxs-lookup"><span data-stu-id="e870b-109">Notify when any token moves.</span></span>|  
|`MDNotifyNone`|<span data-ttu-id="e870b-110">Не уведомлять о перемещении маркера.</span><span class="sxs-lookup"><span data-stu-id="e870b-110">Do not notify when tokens move.</span></span>|  
|`MDNotifyMethodDef`|<span data-ttu-id="e870b-111">Отправить уведомление при `mdMethodDef` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-111">Notify when an `mdMethodDef` token moves.</span></span>|  
|`MDNotifyMemberRef`|<span data-ttu-id="e870b-112">Отправить уведомление при `mdMemberRef` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-112">Notify when an `mdMemberRef` token moves.</span></span>|  
|`MDNotifyFieldDef`|<span data-ttu-id="e870b-113">Отправить уведомление при `mdFieldDef` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-113">Notify when an `mdFieldDef` token moves.</span></span>|  
|`MDNotifyTypeRef`|<span data-ttu-id="e870b-114">Отправить уведомление при `mdTypeRef` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-114">Notify when an `mdTypeRef` token moves.</span></span>|  
|`MDNotifyTypeDef`|<span data-ttu-id="e870b-115">Отправить уведомление при `mdTypeDef` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-115">Notify when an `mdTypeDef` token moves.</span></span>|  
|`MDNotifyParamDef`|<span data-ttu-id="e870b-116">Отправить уведомление при `mdParamDef` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-116">Notify when an `mdParamDef` token moves.</span></span>|  
|`MDNotifyInterfaceImpl`|<span data-ttu-id="e870b-117">Отправить уведомление при `mdInterfaceImpl` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-117">Notify when an `mdInterfaceImpl` token moves.</span></span>|  
|`MDNotifyProperty`|<span data-ttu-id="e870b-118">Отправить уведомление при `mdProperty` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-118">Notify when an `mdProperty` token moves.</span></span>|  
|`MDNotifyEvent`|<span data-ttu-id="e870b-119">Отправить уведомление при `mdEvent` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-119">Notify when an `mdEvent` token moves.</span></span>|  
|`MDNotifySignature`|<span data-ttu-id="e870b-120">Отправить уведомление при `mdSignature` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-120">Notify when an `mdSignature` token moves.</span></span>|  
|`MDNotifyTypeSpec`|<span data-ttu-id="e870b-121">Отправить уведомление при `mdTypeSpec` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-121">Notify when an `mdTypeSpec` token moves.</span></span>|  
|`MDNotifyCustomAttribute`|<span data-ttu-id="e870b-122">Отправить уведомление при `mdCustomAttribute` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-122">Notify when an `mdCustomAttribute` token moves.</span></span>|  
|`MDNotifySecurityValue`|<span data-ttu-id="e870b-123">Отправить уведомление при `mdSecurityValue` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-123">Notify when an `mdSecurityValue` token moves.</span></span>|  
|`MDNotifyPermission`|<span data-ttu-id="e870b-124">Отправить уведомление при `mdPermission` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-124">Notify when an `mdPermission` token moves.</span></span>|  
|`MDNotifyModuleRef`|<span data-ttu-id="e870b-125">Отправить уведомление при `mdModuleRef` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-125">Notify when an `mdModuleRef` token moves.</span></span>|  
|`MDNotifyNameSpace`|<span data-ttu-id="e870b-126">Отправить уведомление при `mdNameSpace` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-126">Notify when an `mdNameSpace` token moves.</span></span>|  
|`MDNotifyAssemblyRef`|<span data-ttu-id="e870b-127">Отправить уведомление при `mdAssemblyRef` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-127">Notify when an `mdAssemblyRef` token moves.</span></span>|  
|`MDNotifyFile`|<span data-ttu-id="e870b-128">Отправить уведомление при `mdFile` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-128">Notify when an `mdFile` token moves.</span></span>|  
|`MDNotifyExportedType`|<span data-ttu-id="e870b-129">Отправить уведомление при `mdExportedType` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-129">Notify when an `mdExportedType` token moves.</span></span>|  
|`MDNotifyResource`|<span data-ttu-id="e870b-130">Отправить уведомление при `mdManifestResource` маркера перемещения.</span><span class="sxs-lookup"><span data-stu-id="e870b-130">Notify when an `mdManifestResource` token moves.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e870b-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="e870b-131">Remarks</span></span>  
 <span data-ttu-id="e870b-132">Маркер можно сопоставить повторно (иными словами переместить) во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="e870b-132">A token may be re-mapped (that is, moved) during a metadata merge.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e870b-133">Требования</span><span class="sxs-lookup"><span data-stu-id="e870b-133">Requirements</span></span>  
 <span data-ttu-id="e870b-134">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e870b-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e870b-135">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="e870b-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e870b-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e870b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e870b-137">См. также</span><span class="sxs-lookup"><span data-stu-id="e870b-137">See Also</span></span>  
 [<span data-ttu-id="e870b-138">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="e870b-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
