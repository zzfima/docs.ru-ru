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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d04f5589ecffbcde59a6ffbe4f3d6c5f0b1040cd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074876"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="37515-102">Перечисление CorCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="37515-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="37515-103">Указывает, будет проверить наличие дублирующихся маркеры метаданных.</span><span class="sxs-lookup"><span data-stu-id="37515-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37515-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37515-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="37515-105">Участники</span><span class="sxs-lookup"><span data-stu-id="37515-105">Members</span></span>  
  
|<span data-ttu-id="37515-106">Член</span><span class="sxs-lookup"><span data-stu-id="37515-106">Member</span></span>|<span data-ttu-id="37515-107">Описание</span><span class="sxs-lookup"><span data-stu-id="37515-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="37515-108">Проверьте все токены метаданных повторяющихся значений.</span><span class="sxs-lookup"><span data-stu-id="37515-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="37515-109">Не используется.</span><span class="sxs-lookup"><span data-stu-id="37515-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="37515-110">Не устанавливайте флажок Поиск дубликатов маркеров метаданных.</span><span class="sxs-lookup"><span data-stu-id="37515-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="37515-111">Выполните поиск дубликатов `mdTypeDef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="37515-112">Выполните поиск дубликатов `mdInterfaceImpl` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="37515-113">Выполните поиск дубликатов `mdMethodDef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="37515-114">Выполните поиск дубликатов `mdTypeRef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="37515-115">Выполните поиск дубликатов `mdMemberRef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="37515-116">Выполните поиск дубликатов `mdCustomAttribute` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="37515-117">Выполните поиск дубликатов `mdParamDef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="37515-118">Выполните поиск дубликатов `mdPermission` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="37515-119">Выполните поиск дубликатов `mdProperty` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="37515-120">Выполните поиск дубликатов `mdEvent` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="37515-121">Выполните поиск дубликатов `mdFieldDef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="37515-122">Выполните поиск дубликатов `mdSignature` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="37515-123">Выполните поиск дубликатов `mdModuleRef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="37515-124">Выполните поиск дубликатов `mdTypeSpec` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="37515-125">Выполните поиск дубликатов `mdImplMap` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="37515-126">Выполните поиск дубликатов `mdAssemblyRef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="37515-127">Выполните поиск дубликатов `mdFile` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="37515-128">Выполните поиск дубликатов `mdExportedType` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="37515-129">Выполните поиск дубликатов `mdManifestResource` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="37515-130">Выполните поиск дубликатов `mdGenericParam` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="37515-131">Выполните поиск дубликатов `mdMethodSpec` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="37515-132">Выполните поиск дубликатов `mdGenericParamConstraint` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="37515-133">Выполните поиск дубликатов `mdAssembly` маркеры.</span><span class="sxs-lookup"><span data-stu-id="37515-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="37515-134">Выполните поиск дубликатов `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, и `mdMethodSpec` маркеров.</span><span class="sxs-lookup"><span data-stu-id="37515-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="37515-135">Требования</span><span class="sxs-lookup"><span data-stu-id="37515-135">Requirements</span></span>  
 <span data-ttu-id="37515-136">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37515-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37515-137">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="37515-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="37515-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37515-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37515-139">См. также</span><span class="sxs-lookup"><span data-stu-id="37515-139">See also</span></span>

- [<span data-ttu-id="37515-140">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="37515-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
