---
title: "Метод IMetaDataEmit::DefineTypeRefByName"
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
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 46b9fe83a5beb031d4ac21deb903060e2f788e1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="84153-102">Метод IMetaDataEmit::DefineTypeRefByName</span><span class="sxs-lookup"><span data-stu-id="84153-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="84153-103">Получает маркер метаданных для типа, определенного в указанной области, которое находится за пределами текущей области.</span><span class="sxs-lookup"><span data-stu-id="84153-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84153-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84153-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84153-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84153-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="84153-106">[in] Токен, указывая область разрешения.</span><span class="sxs-lookup"><span data-stu-id="84153-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="84153-107">Допустимы следующие типы токенов:</span><span class="sxs-lookup"><span data-stu-id="84153-107">The following token types are valid:</span></span>  
  
-   <span data-ttu-id="84153-108">`mdModuleRef`, если тип определен в той же сборке, в которой определен вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="84153-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="84153-109">`mdAssemblyRef`, если тип определен в сборке, отличной от той, в которой определен вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="84153-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="84153-110">`mdTypeRef`, если тип является вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="84153-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
-   <span data-ttu-id="84153-111">`mdModule`, если тип определен в том же модуле, в котором определен вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="84153-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="84153-112">Значение NULL, если тип определен глобально.</span><span class="sxs-lookup"><span data-stu-id="84153-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="84153-113">[in] Имя типа целевого объекта в формате Юникод.</span><span class="sxs-lookup"><span data-stu-id="84153-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="84153-114">[out] Указатель на `mdTypeRef` маркер, который назначен тип.</span><span class="sxs-lookup"><span data-stu-id="84153-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84153-115">Требования</span><span class="sxs-lookup"><span data-stu-id="84153-115">Requirements</span></span>  
 <span data-ttu-id="84153-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84153-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84153-117">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="84153-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="84153-118">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="84153-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84153-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84153-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84153-120">См. также</span><span class="sxs-lookup"><span data-stu-id="84153-120">See Also</span></span>  
 [<span data-ttu-id="84153-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="84153-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="84153-122">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="84153-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
