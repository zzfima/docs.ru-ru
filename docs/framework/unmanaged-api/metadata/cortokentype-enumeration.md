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
ms.openlocfilehash: 74807a678b5c0c2738f33fe552f6462af93ca1f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436465"
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="7ecdf-102">Перечисление CorTokenType</span><span class="sxs-lookup"><span data-stu-id="7ecdf-102">CorTokenType Enumeration</span></span>
<span data-ttu-id="7ecdf-103">Указывает тип маркера метаданных.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ecdf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ecdf-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="7ecdf-105">Члены</span><span class="sxs-lookup"><span data-stu-id="7ecdf-105">Members</span></span>  
  
|<span data-ttu-id="7ecdf-106">Член</span><span class="sxs-lookup"><span data-stu-id="7ecdf-106">Member</span></span>|<span data-ttu-id="7ecdf-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7ecdf-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="7ecdf-108">Токен `mdModule`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="7ecdf-109">Токен `mdTypeRef`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="7ecdf-110">Токен `mdTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="7ecdf-111">Токен `mdFieldDef`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="7ecdf-112">Токен `mdMethodDef`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="7ecdf-113">Токен `mdParamDef`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="7ecdf-114">Токен `mdInterfaceImpl`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="7ecdf-115">Токен `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="7ecdf-116">Токен `mdCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="7ecdf-117">Токен `mdPermission`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="7ecdf-118">Токен `mdSignature`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="7ecdf-119">Токен `mdEvent`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="7ecdf-120">Токен `mdProperty`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="7ecdf-121">Токен `mdModuleRef`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="7ecdf-122">Токен `mdTypeSpec`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="7ecdf-123">Токен `mdAssembly`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="7ecdf-124">Токен `mdAssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="7ecdf-125">Токен `mdFile`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="7ecdf-126">Токен `mdExportedType`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="7ecdf-127">Токен `mdManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="7ecdf-128">Токен `mdGenericParam`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="7ecdf-129">Токен `mdMethodSpec`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="7ecdf-130">Токен `mdGenericParamConstraint`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="7ecdf-131">Токен `mdString`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="7ecdf-132">Токен `mdName`.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="7ecdf-133">Не используется.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ecdf-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ecdf-134">Remarks</span></span>  
 <span data-ttu-id="7ecdf-135">Каждое значение равно значению верхнего байта в соответствующем маркере метаданных.</span><span class="sxs-lookup"><span data-stu-id="7ecdf-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ecdf-136">Требования</span><span class="sxs-lookup"><span data-stu-id="7ecdf-136">Requirements</span></span>  
 <span data-ttu-id="7ecdf-137">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ecdf-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ecdf-138">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="7ecdf-138">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7ecdf-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ecdf-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ecdf-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="7ecdf-140">See also</span></span>

- [<span data-ttu-id="7ecdf-141">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="7ecdf-141">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
