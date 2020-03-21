---
title: Метод IMetaDataEmit::SaveToMemory
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
ms.openlocfilehash: d8843b2b5f69696dc206e9b530e3062ff225e89e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177580"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="b1dde-102">Метод IMetaDataEmit::SaveToMemory</span><span class="sxs-lookup"><span data-stu-id="b1dde-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="b1dde-103">Сохраняет все метаданные в текущем диапазоне в заданную область памяти.</span><span class="sxs-lookup"><span data-stu-id="b1dde-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1dde-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1dde-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1dde-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1dde-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="b1dde-106">(ваут) Адрес, по которому можно начать писать метаданные.</span><span class="sxs-lookup"><span data-stu-id="b1dde-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="b1dde-107">(в) Размер, в байтах, выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="b1dde-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1dde-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b1dde-108">Requirements</span></span>  
 <span data-ttu-id="b1dde-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1dde-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1dde-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b1dde-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b1dde-111">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b1dde-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1dde-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1dde-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1dde-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b1dde-113">See also</span></span>

- [<span data-ttu-id="b1dde-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b1dde-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b1dde-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b1dde-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
