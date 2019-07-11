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
ms.openlocfilehash: b64275def01d7b62f9a461de69a286769094305e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777584"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="a2760-102">Метод IMetaDataEmit::DefineMethodImpl</span><span class="sxs-lookup"><span data-stu-id="a2760-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="a2760-103">Создает определение реализации метода, унаследованного от интерфейса и возвращает маркер для этого определения реализации метода.</span><span class="sxs-lookup"><span data-stu-id="a2760-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2760-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2760-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2760-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2760-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="a2760-106">[in] `mdTypedef` Маркеров реализующего класса.</span><span class="sxs-lookup"><span data-stu-id="a2760-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="a2760-107">[in] `mdMethodDef` Или `mdMemberRef` маркера тела кода.</span><span class="sxs-lookup"><span data-stu-id="a2760-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="a2760-108">[in] `mdMethodDef` Или `mdMemberRef` маркера реализации метода интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a2760-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2760-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a2760-109">Requirements</span></span>  
 <span data-ttu-id="a2760-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2760-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2760-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a2760-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a2760-112">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2760-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2760-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2760-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2760-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a2760-114">See also</span></span>

- [<span data-ttu-id="a2760-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a2760-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a2760-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a2760-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
