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
ms.openlocfilehash: 99f529a151a42cf4a9ee1f74bd3a76a5b6b1b35f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445261"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="07254-102">Метод IMetaDataEmit::DefineMethodImpl</span><span class="sxs-lookup"><span data-stu-id="07254-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="07254-103">Создает определение для реализации метода, унаследованного от интерфейса, и возвращает маркер для этого определения реализации метода.</span><span class="sxs-lookup"><span data-stu-id="07254-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07254-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="07254-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07254-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="07254-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="07254-106">окне Токен `mdTypedef` реализующего класса.</span><span class="sxs-lookup"><span data-stu-id="07254-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="07254-107">окне Маркер `mdMethodDef` или `mdMemberRef` текста кода.</span><span class="sxs-lookup"><span data-stu-id="07254-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="07254-108">окне Токен `mdMethodDef` или `mdMemberRef` реализуемого метода интерфейса.</span><span class="sxs-lookup"><span data-stu-id="07254-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07254-109">Требования</span><span class="sxs-lookup"><span data-stu-id="07254-109">Requirements</span></span>  
 <span data-ttu-id="07254-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07254-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07254-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="07254-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07254-112">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="07254-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07254-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07254-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07254-114">См. также</span><span class="sxs-lookup"><span data-stu-id="07254-114">See also</span></span>

- [<span data-ttu-id="07254-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="07254-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="07254-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="07254-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
