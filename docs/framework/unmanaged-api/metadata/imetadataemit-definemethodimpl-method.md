---
title: Метод IMetaDataEmit::DefineMethodImpl
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05b2530bde2f4532e94610a683e7bbc2f59540aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178390"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="c6f7c-102">Метод IMetaDataEmit::DefineMethodImpl</span><span class="sxs-lookup"><span data-stu-id="c6f7c-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="c6f7c-103">Создает определение реализации метода, унаследованного от интерфейса и возвращает маркер для этого определения реализации метода.</span><span class="sxs-lookup"><span data-stu-id="c6f7c-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6f7c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6f7c-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6f7c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c6f7c-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="c6f7c-106">[in] `mdTypedef` Маркеров реализующего класса.</span><span class="sxs-lookup"><span data-stu-id="c6f7c-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="c6f7c-107">[in] `mdMethodDef` Или `mdMethodRef` маркера тела кода.</span><span class="sxs-lookup"><span data-stu-id="c6f7c-107">[in] The `mdMethodDef` or `mdMethodRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="c6f7c-108">[in] `mdMethodDef` Или `mdMethodRef` маркера реализации метода интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c6f7c-108">[in] The `mdMethodDef` or `mdMethodRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6f7c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c6f7c-109">Requirements</span></span>  
 <span data-ttu-id="c6f7c-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6f7c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6f7c-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c6f7c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6f7c-112">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c6f7c-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6f7c-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6f7c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6f7c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c6f7c-114">See also</span></span>

- [<span data-ttu-id="c6f7c-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c6f7c-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c6f7c-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c6f7c-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
