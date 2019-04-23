---
title: Перечисление CorTokenType
ms.date: 03/30/2017
api_name:
- CorTokenType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTokenType
helpviewer_keywords:
- CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1b33b50e53c454f2b62253d12943ea044240d8cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230516"
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="c6b72-102">Перечисление CorTokenType</span><span class="sxs-lookup"><span data-stu-id="c6b72-102">CorTokenType Enumeration</span></span>
<span data-ttu-id="c6b72-103">Указывает тип маркера метаданных.</span><span class="sxs-lookup"><span data-stu-id="c6b72-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6b72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6b72-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c6b72-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c6b72-105">Members</span></span>  
  
|<span data-ttu-id="c6b72-106">Член</span><span class="sxs-lookup"><span data-stu-id="c6b72-106">Member</span></span>|<span data-ttu-id="c6b72-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c6b72-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="c6b72-108">`mdModule` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="c6b72-109">`mdTypeRef` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="c6b72-110">`mdTypeDef` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="c6b72-111">`mdFieldDef` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="c6b72-112">`mdMethodDef` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="c6b72-113">`mdParamDef` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="c6b72-114">`mdInterfaceImpl` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="c6b72-115">`mdMemberRef` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="c6b72-116">`mdCustomAttribute` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="c6b72-117">`mdPermission` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="c6b72-118">`mdSignature` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="c6b72-119">`mdEvent` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="c6b72-120">`mdProperty` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="c6b72-121">`mdModuleRef` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="c6b72-122">`mdTypeSpec` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="c6b72-123">`mdAssembly` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="c6b72-124">`mdAssemblyRef` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="c6b72-125">`mdFile` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="c6b72-126">`mdExportedType` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="c6b72-127">`mdManifestResource` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="c6b72-128">`mdGenericParam` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="c6b72-129">`mdMethodSpec` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="c6b72-130">`mdGenericParamConstraint` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="c6b72-131">`mdString` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="c6b72-132">`mdName` Токена.</span><span class="sxs-lookup"><span data-stu-id="c6b72-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="c6b72-133">Не используется.</span><span class="sxs-lookup"><span data-stu-id="c6b72-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6b72-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6b72-134">Remarks</span></span>  
 <span data-ttu-id="c6b72-135">Каждое значение равно значению старший байт в соответствующий маркер метаданных.</span><span class="sxs-lookup"><span data-stu-id="c6b72-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6b72-136">Требования</span><span class="sxs-lookup"><span data-stu-id="c6b72-136">Requirements</span></span>  
 <span data-ttu-id="c6b72-137">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6b72-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6b72-138">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c6b72-138">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c6b72-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6b72-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6b72-140">См. также</span><span class="sxs-lookup"><span data-stu-id="c6b72-140">See also</span></span>

- [<span data-ttu-id="c6b72-141">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="c6b72-141">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
