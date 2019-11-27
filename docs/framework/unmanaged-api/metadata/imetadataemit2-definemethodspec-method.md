---
title: Метод IMetaDataEmit2::DefineMethodSpec
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
ms.openlocfilehash: 7547d7557169b1279125141afb5b05e22341942a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432740"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="903d7-102">Метод IMetaDataEmit2::DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="903d7-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="903d7-103">Создает универсальный экземпляр метода и получает маркер для определения.</span><span class="sxs-lookup"><span data-stu-id="903d7-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="903d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="903d7-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="903d7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="903d7-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="903d7-106">окне Токен для метода, для которого создается универсальный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="903d7-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="903d7-107">Токен должен иметь тип `mdMethodDef` или `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="903d7-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="903d7-108">окне Указатель на двоичную сигнатуру COM+ метода.</span><span class="sxs-lookup"><span data-stu-id="903d7-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="903d7-109">окне Размер `pvSigBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="903d7-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="903d7-110">заполняет Токен для определения сигнатуры метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="903d7-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="903d7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="903d7-111">Requirements</span></span>  
 <span data-ttu-id="903d7-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="903d7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="903d7-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="903d7-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="903d7-114">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="903d7-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="903d7-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="903d7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="903d7-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="903d7-116">See also</span></span>

- [<span data-ttu-id="903d7-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="903d7-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="903d7-118">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="903d7-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
