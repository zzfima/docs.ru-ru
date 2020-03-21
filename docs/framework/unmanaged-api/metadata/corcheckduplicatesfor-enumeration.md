---
title: Перечисление CorCheckDuplicatesFor
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
ms.openlocfilehash: 04dc12ab4d7d178ebf1575a3260f9f4981972782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176192"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="fba20-102">Перечисление CorCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="fba20-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="fba20-103">Определяет токены метаданных, которые будут проверены на наличие дубликатов.</span><span class="sxs-lookup"><span data-stu-id="fba20-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fba20-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fba20-104">Syntax</span></span>  
  
```cpp  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a><span data-ttu-id="fba20-105">Члены</span><span class="sxs-lookup"><span data-stu-id="fba20-105">Members</span></span>  
  
|<span data-ttu-id="fba20-106">Участник</span><span class="sxs-lookup"><span data-stu-id="fba20-106">Member</span></span>|<span data-ttu-id="fba20-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fba20-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="fba20-108">Проверьте все токены метаданных на наличие дубликатов.</span><span class="sxs-lookup"><span data-stu-id="fba20-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="fba20-109">Не используется.</span><span class="sxs-lookup"><span data-stu-id="fba20-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="fba20-110">Не проверяйте токены метаданных на наличие дубликатов.</span><span class="sxs-lookup"><span data-stu-id="fba20-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="fba20-111">Проверьте наличие `mdTypeDef` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="fba20-112">Проверьте наличие `mdInterfaceImpl` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="fba20-113">Проверьте наличие `mdMethodDef` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="fba20-114">Проверьте наличие `mdTypeRef` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="fba20-115">Проверьте наличие `mdMemberRef` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="fba20-116">Проверьте наличие `mdCustomAttribute` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="fba20-117">Проверьте наличие `mdParamDef` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="fba20-118">Проверьте наличие `mdPermission` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="fba20-119">Проверьте наличие `mdProperty` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="fba20-120">Проверьте наличие `mdEvent` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="fba20-121">Проверьте наличие `mdFieldDef` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="fba20-122">Проверьте наличие `mdSignature` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="fba20-123">Проверьте наличие `mdModuleRef` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="fba20-124">Проверьте наличие `mdTypeSpec` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="fba20-125">Проверьте наличие `mdImplMap` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="fba20-126">Проверьте наличие `mdAssemblyRef` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="fba20-127">Проверьте наличие `mdFile` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="fba20-128">Проверьте наличие `mdExportedType` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="fba20-129">Проверьте наличие `mdManifestResource` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="fba20-130">Проверьте наличие `mdGenericParam` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="fba20-131">Проверьте наличие `mdMethodSpec` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="fba20-132">Проверьте наличие `mdGenericParamConstraint` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="fba20-133">Проверьте наличие `mdAssembly` дубликатов токенов.</span><span class="sxs-lookup"><span data-stu-id="fba20-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="fba20-134">`mdMemberRef`Проверьте дубликаты, `mdSignature` `mdTypeRef` `mdTypeSpec`, `mdMethodSpec` , и жетоны.</span><span class="sxs-lookup"><span data-stu-id="fba20-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fba20-135">Требования</span><span class="sxs-lookup"><span data-stu-id="fba20-135">Requirements</span></span>  
 <span data-ttu-id="fba20-136">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fba20-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fba20-137">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="fba20-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="fba20-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fba20-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fba20-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fba20-139">See also</span></span>

- [<span data-ttu-id="fba20-140">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="fba20-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
