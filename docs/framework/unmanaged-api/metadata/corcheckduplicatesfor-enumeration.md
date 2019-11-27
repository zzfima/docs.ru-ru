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
ms.openlocfilehash: 6b551743227dc1c6069796038782a515e6dbe8c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443787"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="281fe-102">Перечисление CorCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="281fe-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="281fe-103">Указывает маркеры метаданных, которые будут проверяться на наличие дубликатов.</span><span class="sxs-lookup"><span data-stu-id="281fe-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="281fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="281fe-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="281fe-105">Члены</span><span class="sxs-lookup"><span data-stu-id="281fe-105">Members</span></span>  
  
|<span data-ttu-id="281fe-106">Член</span><span class="sxs-lookup"><span data-stu-id="281fe-106">Member</span></span>|<span data-ttu-id="281fe-107">Описание</span><span class="sxs-lookup"><span data-stu-id="281fe-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="281fe-108">Проверьте все маркеры метаданных на наличие дубликатов.</span><span class="sxs-lookup"><span data-stu-id="281fe-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="281fe-109">Не используется.</span><span class="sxs-lookup"><span data-stu-id="281fe-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="281fe-110">Не проверяйте маркеры метаданных для дубликатов.</span><span class="sxs-lookup"><span data-stu-id="281fe-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="281fe-111">Проверьте наличие дубликатов токенов `mdTypeDef`.</span><span class="sxs-lookup"><span data-stu-id="281fe-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="281fe-112">Проверьте наличие дубликатов токенов `mdInterfaceImpl`.</span><span class="sxs-lookup"><span data-stu-id="281fe-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="281fe-113">Проверьте наличие дубликатов токенов `mdMethodDef`.</span><span class="sxs-lookup"><span data-stu-id="281fe-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="281fe-114">Проверьте наличие дубликатов токенов `mdTypeRef`.</span><span class="sxs-lookup"><span data-stu-id="281fe-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="281fe-115">Проверьте наличие дубликатов токенов `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="281fe-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="281fe-116">Проверьте наличие дубликатов токенов `mdCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="281fe-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="281fe-117">Проверьте наличие дубликатов токенов `mdParamDef`.</span><span class="sxs-lookup"><span data-stu-id="281fe-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="281fe-118">Проверьте наличие дубликатов токенов `mdPermission`.</span><span class="sxs-lookup"><span data-stu-id="281fe-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="281fe-119">Проверьте наличие дубликатов токенов `mdProperty`.</span><span class="sxs-lookup"><span data-stu-id="281fe-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="281fe-120">Проверьте наличие дубликатов токенов `mdEvent`.</span><span class="sxs-lookup"><span data-stu-id="281fe-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="281fe-121">Проверьте наличие дубликатов токенов `mdFieldDef`.</span><span class="sxs-lookup"><span data-stu-id="281fe-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="281fe-122">Проверьте наличие дубликатов токенов `mdSignature`.</span><span class="sxs-lookup"><span data-stu-id="281fe-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="281fe-123">Проверьте наличие дубликатов токенов `mdModuleRef`.</span><span class="sxs-lookup"><span data-stu-id="281fe-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="281fe-124">Проверьте наличие дубликатов токенов `mdTypeSpec`.</span><span class="sxs-lookup"><span data-stu-id="281fe-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="281fe-125">Проверьте наличие дубликатов токенов `mdImplMap`.</span><span class="sxs-lookup"><span data-stu-id="281fe-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="281fe-126">Проверьте наличие дубликатов токенов `mdAssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="281fe-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="281fe-127">Проверьте наличие дубликатов токенов `mdFile`.</span><span class="sxs-lookup"><span data-stu-id="281fe-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="281fe-128">Проверьте наличие дубликатов токенов `mdExportedType`.</span><span class="sxs-lookup"><span data-stu-id="281fe-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="281fe-129">Проверьте наличие дубликатов токенов `mdManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="281fe-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="281fe-130">Проверьте наличие дубликатов токенов `mdGenericParam`.</span><span class="sxs-lookup"><span data-stu-id="281fe-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="281fe-131">Проверьте наличие дубликатов токенов `mdMethodSpec`.</span><span class="sxs-lookup"><span data-stu-id="281fe-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="281fe-132">Проверьте наличие дубликатов токенов `mdGenericParamConstraint`.</span><span class="sxs-lookup"><span data-stu-id="281fe-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="281fe-133">Проверьте наличие дубликатов токенов `mdAssembly`.</span><span class="sxs-lookup"><span data-stu-id="281fe-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="281fe-134">Проверьте наличие дубликатов `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`и маркеров `mdMethodSpec`.</span><span class="sxs-lookup"><span data-stu-id="281fe-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="281fe-135">Требования</span><span class="sxs-lookup"><span data-stu-id="281fe-135">Requirements</span></span>  
 <span data-ttu-id="281fe-136">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="281fe-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="281fe-137">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="281fe-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="281fe-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="281fe-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="281fe-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="281fe-139">See also</span></span>

- [<span data-ttu-id="281fe-140">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="281fe-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
