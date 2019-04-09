---
title: Метод IMetaDataEmit::DefineTypeRefByName
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d93c55cec3d35fd4208a4a8a7c9b235dd10fb9ca
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156173"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="a045e-102">Метод IMetaDataEmit::DefineTypeRefByName</span><span class="sxs-lookup"><span data-stu-id="a045e-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="a045e-103">Получает маркер метаданных для типа, который определен в заданной области, которая выходит за пределы текущей области.</span><span class="sxs-lookup"><span data-stu-id="a045e-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a045e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a045e-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a045e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a045e-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="a045e-106">[in] Токен, определяющий область разрешения.</span><span class="sxs-lookup"><span data-stu-id="a045e-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="a045e-107">Допустимы следующие типы токенов:</span><span class="sxs-lookup"><span data-stu-id="a045e-107">The following token types are valid:</span></span>  
  
-   `mdModuleRef`<span data-ttu-id="a045e-108">, если тип определен в той же сборке, в котором определен вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="a045e-108">, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
-   `mdAssemblyRef`<span data-ttu-id="a045e-109">, если тип определен в сборке, отличной от той, в котором определен вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="a045e-109">, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
-   `mdTypeRef`<span data-ttu-id="a045e-110">, если тип является вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="a045e-110">, if the type is a nested type.</span></span>  
  
-   `mdModule`<span data-ttu-id="a045e-111">, если тип определен в том же модуле, в котором определен вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="a045e-111">, if the type is defined in the same module in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="a045e-112">Значение NULL, если тип определен глобально.</span><span class="sxs-lookup"><span data-stu-id="a045e-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="a045e-113">[in] Имя типа целевого объекта в формате Юникод.</span><span class="sxs-lookup"><span data-stu-id="a045e-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="a045e-114">[out] Указатель на `mdTypeRef` токен, который присваивается тип.</span><span class="sxs-lookup"><span data-stu-id="a045e-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a045e-115">Требования</span><span class="sxs-lookup"><span data-stu-id="a045e-115">Requirements</span></span>  
 <span data-ttu-id="a045e-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a045e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a045e-117">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a045e-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a045e-118">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a045e-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a045e-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a045e-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a045e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a045e-120">See also</span></span>

- [<span data-ttu-id="a045e-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a045e-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a045e-122">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a045e-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
