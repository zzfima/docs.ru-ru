---
title: Метод IMetaDataImport2::GetGenericParamConstraintProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamConstraintProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e0503c5bd924793df8143c89e358618fb8844c6c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215122"
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="9485a-102">Метод IMetaDataImport2::GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="9485a-102">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>
<span data-ttu-id="9485a-103">Получает метаданные, связанные с ограничением параметра универсального типа, представленного маркером указанное ограничение.</span><span class="sxs-lookup"><span data-stu-id="9485a-103">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9485a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9485a-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9485a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9485a-105">Parameters</span></span>  
 `gpc`  
 <span data-ttu-id="9485a-106">[in] Токен, ограничение универсального параметра, для которого необходимо вернуть метаданные.</span><span class="sxs-lookup"><span data-stu-id="9485a-106">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="9485a-107">[out] Указатель на токен, представляющий универсальный параметр, который ограничен.</span><span class="sxs-lookup"><span data-stu-id="9485a-107">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="9485a-108">[out] Указатель на токен TypeDef, TypeRef или TypeSpec, который представляет ограничение на `ptGenericParam`.</span><span class="sxs-lookup"><span data-stu-id="9485a-108">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9485a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9485a-109">Requirements</span></span>  
 <span data-ttu-id="9485a-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9485a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9485a-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9485a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9485a-112">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9485a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9485a-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9485a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9485a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9485a-114">See also</span></span>

- [<span data-ttu-id="9485a-115">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9485a-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="9485a-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9485a-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
