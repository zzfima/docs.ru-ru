---
title: "Метод IMetaDataImport2::GetGenericParamConstraintProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetGenericParamConstraintProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7d1e560dd511758652e1acbc262b4ddc3efdd12c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="78832-102">Метод IMetaDataImport2::GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="78832-102">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>
<span data-ttu-id="78832-103">Возвращает метаданные, связанные с ограничением параметра универсального типа, представленного маркером указанное ограничение.</span><span class="sxs-lookup"><span data-stu-id="78832-103">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78832-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78832-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="78832-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="78832-105">Parameters</span></span>  
 `gpc`  
 <span data-ttu-id="78832-106">[in] Токен для ограничения универсального параметра, для которого необходимо возвратить метаданные.</span><span class="sxs-lookup"><span data-stu-id="78832-106">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="78832-107">[out] Указатель на токен, представляющий универсальный параметр, который ограничен.</span><span class="sxs-lookup"><span data-stu-id="78832-107">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="78832-108">[out] Указатель на маркер TypeDef, TypeRef или TypeSpec, который представляет ограничение на `ptGenericParam`.</span><span class="sxs-lookup"><span data-stu-id="78832-108">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78832-109">Требования</span><span class="sxs-lookup"><span data-stu-id="78832-109">Requirements</span></span>  
 <span data-ttu-id="78832-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78832-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78832-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="78832-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="78832-112">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="78832-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="78832-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78832-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78832-114">См. также</span><span class="sxs-lookup"><span data-stu-id="78832-114">See Also</span></span>  
 [<span data-ttu-id="78832-115">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="78832-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="78832-116">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="78832-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
