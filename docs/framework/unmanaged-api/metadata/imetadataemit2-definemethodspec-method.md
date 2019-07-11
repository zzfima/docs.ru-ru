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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a4185ec41fc9f7d1d919a79b57c02625210ad72a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777191"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="75b6a-102">Метод IMetaDataEmit2::DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="75b6a-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="75b6a-103">Создает экземпляр универсального метода и возвращает маркер для определения.</span><span class="sxs-lookup"><span data-stu-id="75b6a-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75b6a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75b6a-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75b6a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="75b6a-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="75b6a-106">[in] Токен, для которого необходимо создать экземпляр универсального метода.</span><span class="sxs-lookup"><span data-stu-id="75b6a-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="75b6a-107">Токен должен иметь тип `mdMethodDef` или `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="75b6a-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="75b6a-108">[in] Указатель на двоичную подпись COM + метода.</span><span class="sxs-lookup"><span data-stu-id="75b6a-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="75b6a-109">[in] Размер в байтах из `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="75b6a-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="75b6a-110">[out] Маркер для определения сигнатуры метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="75b6a-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75b6a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="75b6a-111">Requirements</span></span>  
 <span data-ttu-id="75b6a-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75b6a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75b6a-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="75b6a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="75b6a-114">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="75b6a-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="75b6a-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75b6a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75b6a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="75b6a-116">See also</span></span>

- [<span data-ttu-id="75b6a-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="75b6a-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="75b6a-118">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="75b6a-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
