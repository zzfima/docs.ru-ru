---
title: Метод IMetaDataImport::GetNestedClassProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
ms.openlocfilehash: 0adf4f91e1bc7bfb72f634cb3bf038710198b74f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437138"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="8c109-102">Метод IMetaDataImport::GetNestedClassProps</span><span class="sxs-lookup"><span data-stu-id="8c109-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="8c109-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span><span class="sxs-lookup"><span data-stu-id="8c109-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c109-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c109-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c109-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c109-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="8c109-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span><span class="sxs-lookup"><span data-stu-id="8c109-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="8c109-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span><span class="sxs-lookup"><span data-stu-id="8c109-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c109-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8c109-108">Requirements</span></span>  
 <span data-ttu-id="8c109-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c109-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c109-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8c109-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c109-111">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8c109-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8c109-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c109-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c109-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8c109-113">See also</span></span>

- [<span data-ttu-id="8c109-114">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="8c109-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8c109-115">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="8c109-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
