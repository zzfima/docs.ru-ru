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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074876"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="cc8b0-102">Перечисление CorCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="cc8b0-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="cc8b0-103">Указывает, будет проверить наличие дублирующихся маркеры метаданных.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc8b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc8b0-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="cc8b0-105">Участники</span><span class="sxs-lookup"><span data-stu-id="cc8b0-105">Members</span></span>  
  
|<span data-ttu-id="cc8b0-106">Член</span><span class="sxs-lookup"><span data-stu-id="cc8b0-106">Member</span></span>|<span data-ttu-id="cc8b0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cc8b0-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="cc8b0-108">Проверьте все токены метаданных повторяющихся значений.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="cc8b0-109">Не используется.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="cc8b0-110">Не устанавливайте флажок Поиск дубликатов маркеров метаданных.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="cc8b0-111">Выполните поиск дубликатов `mdTypeDef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="cc8b0-112">Выполните поиск дубликатов `mdInterfaceImpl` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="cc8b0-113">Выполните поиск дубликатов `mdMethodDef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="cc8b0-114">Выполните поиск дубликатов `mdTypeRef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="cc8b0-115">Выполните поиск дубликатов `mdMemberRef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="cc8b0-116">Выполните поиск дубликатов `mdCustomAttribute` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="cc8b0-117">Выполните поиск дубликатов `mdParamDef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="cc8b0-118">Выполните поиск дубликатов `mdPermission` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="cc8b0-119">Выполните поиск дубликатов `mdProperty` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="cc8b0-120">Выполните поиск дубликатов `mdEvent` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="cc8b0-121">Выполните поиск дубликатов `mdFieldDef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="cc8b0-122">Выполните поиск дубликатов `mdSignature` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="cc8b0-123">Выполните поиск дубликатов `mdModuleRef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="cc8b0-124">Выполните поиск дубликатов `mdTypeSpec` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="cc8b0-125">Выполните поиск дубликатов `mdImplMap` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="cc8b0-126">Выполните поиск дубликатов `mdAssemblyRef` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="cc8b0-127">Выполните поиск дубликатов `mdFile` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="cc8b0-128">Выполните поиск дубликатов `mdExportedType` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="cc8b0-129">Выполните поиск дубликатов `mdManifestResource` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="cc8b0-130">Выполните поиск дубликатов `mdGenericParam` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="cc8b0-131">Выполните поиск дубликатов `mdMethodSpec` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="cc8b0-132">Выполните поиск дубликатов `mdGenericParamConstraint` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="cc8b0-133">Выполните поиск дубликатов `mdAssembly` маркеры.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="cc8b0-134">Выполните поиск дубликатов `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, и `mdMethodSpec` маркеров.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc8b0-135">Требования</span><span class="sxs-lookup"><span data-stu-id="cc8b0-135">Requirements</span></span>  
 <span data-ttu-id="cc8b0-136">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc8b0-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc8b0-137">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="cc8b0-137">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="cc8b0-138">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cc8b0-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cc8b0-139">См. также</span><span class="sxs-lookup"><span data-stu-id="cc8b0-139">See also</span></span>

- [<span data-ttu-id="cc8b0-140">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="cc8b0-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
