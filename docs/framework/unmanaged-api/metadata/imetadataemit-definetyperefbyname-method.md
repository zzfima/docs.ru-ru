---
title: "Метод IMetaDataEmit::DefineTypeRefByName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineTypeRefByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9ce04733fa9f149f155d850c53b65b263943cf8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="441b5-102">Метод IMetaDataEmit::DefineTypeRefByName</span><span class="sxs-lookup"><span data-stu-id="441b5-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="441b5-103">Получает маркер метаданных для типа, определенного в указанной области, которое находится за пределами текущей области.</span><span class="sxs-lookup"><span data-stu-id="441b5-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="441b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="441b5-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="441b5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="441b5-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="441b5-106">[in] Токен, указывая область разрешения.</span><span class="sxs-lookup"><span data-stu-id="441b5-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="441b5-107">Допустимы следующие типы токенов:</span><span class="sxs-lookup"><span data-stu-id="441b5-107">The following token types are valid:</span></span>  
  
-   <span data-ttu-id="441b5-108">`mdModuleRef`, если тип определен в той же сборке, в которой определен вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="441b5-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="441b5-109">`mdAssemblyRef`, если тип определен в сборке, отличной от той, в которой определен вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="441b5-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="441b5-110">`mdTypeRef`, если тип является вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="441b5-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
-   <span data-ttu-id="441b5-111">`mdModule`, если тип определен в том же модуле, в котором определен вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="441b5-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="441b5-112">Значение NULL, если тип определен глобально.</span><span class="sxs-lookup"><span data-stu-id="441b5-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="441b5-113">[in] Имя типа целевого объекта в формате Юникод.</span><span class="sxs-lookup"><span data-stu-id="441b5-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="441b5-114">[out] Указатель на `mdTypeRef` маркер, который назначен тип.</span><span class="sxs-lookup"><span data-stu-id="441b5-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="441b5-115">Требования</span><span class="sxs-lookup"><span data-stu-id="441b5-115">Requirements</span></span>  
 <span data-ttu-id="441b5-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="441b5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="441b5-117">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="441b5-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="441b5-118">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="441b5-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="441b5-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="441b5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="441b5-120">См. также</span><span class="sxs-lookup"><span data-stu-id="441b5-120">See Also</span></span>  
 [<span data-ttu-id="441b5-121">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="441b5-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="441b5-122">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="441b5-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
