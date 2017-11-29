---
title: "Перечисление CorTokenType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorTokenType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorTokenType
helpviewer_keywords: CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1910321942ebac26d8c377f9d156cdf97bd34b62
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="82e81-102">Перечисление CorTokenType</span><span class="sxs-lookup"><span data-stu-id="82e81-102">CorTokenType Enumeration</span></span>
<span data-ttu-id="82e81-103">Указывает тип маркера метаданных.</span><span class="sxs-lookup"><span data-stu-id="82e81-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82e81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82e81-104">Syntax</span></span>  
  
```  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a><span data-ttu-id="82e81-105">Члены</span><span class="sxs-lookup"><span data-stu-id="82e81-105">Members</span></span>  
  
|<span data-ttu-id="82e81-106">Член</span><span class="sxs-lookup"><span data-stu-id="82e81-106">Member</span></span>|<span data-ttu-id="82e81-107">Описание</span><span class="sxs-lookup"><span data-stu-id="82e81-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="82e81-108">`mdModule` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="82e81-109">`mdTypeRef` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="82e81-110">`mdTypeDef` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="82e81-111">`mdFieldDef` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="82e81-112">`mdMethodDef` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="82e81-113">`mdParamDef` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="82e81-114">`mdInterfaceImpl` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="82e81-115">`mdMemberRef` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="82e81-116">`mdCustomAttribute` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="82e81-117">`mdPermission` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="82e81-118">`mdSignature` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="82e81-119">`mdEvent` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="82e81-120">`mdProperty` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="82e81-121">`mdModuleRef` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="82e81-122">`mdTypeSpec` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="82e81-123">`mdAssembly` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="82e81-124">`mdAssemblyRef` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="82e81-125">`mdFile` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="82e81-126">`mdExportedType` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="82e81-127">`mdManifestResource` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="82e81-128">`mdGenericParam` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="82e81-129">`mdMethodSpec` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="82e81-130">`mdGenericParamConstraint` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="82e81-131">`mdString` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="82e81-132">`mdName` Маркеров.</span><span class="sxs-lookup"><span data-stu-id="82e81-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="82e81-133">Не используется.</span><span class="sxs-lookup"><span data-stu-id="82e81-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82e81-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="82e81-134">Remarks</span></span>  
 <span data-ttu-id="82e81-135">Каждое значение равно значению старшего байта в соответствующем маркере метаданных.</span><span class="sxs-lookup"><span data-stu-id="82e81-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82e81-136">Требования</span><span class="sxs-lookup"><span data-stu-id="82e81-136">Requirements</span></span>  
 <span data-ttu-id="82e81-137">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82e81-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82e81-138">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="82e81-138">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="82e81-139">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82e81-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82e81-140">См. также</span><span class="sxs-lookup"><span data-stu-id="82e81-140">See Also</span></span>  
 [<span data-ttu-id="82e81-141">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="82e81-141">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
