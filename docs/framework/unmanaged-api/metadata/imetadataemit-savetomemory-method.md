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
ms.openlocfilehash: be4fb0b4b49408a97b318e0f54f5a753f3f24ef1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435798"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="25868-102">Метод IMetaDataEmit::SaveToMemory</span><span class="sxs-lookup"><span data-stu-id="25868-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="25868-103">Сохраняет все метаданные в текущей области в указанную область памяти.</span><span class="sxs-lookup"><span data-stu-id="25868-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25868-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25868-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25868-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="25868-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="25868-106">заполняет Адрес, с которого начинается запись метаданных.</span><span class="sxs-lookup"><span data-stu-id="25868-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="25868-107">окне Размер выделенной памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="25868-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25868-108">Требования</span><span class="sxs-lookup"><span data-stu-id="25868-108">Requirements</span></span>  
 <span data-ttu-id="25868-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25868-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25868-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="25868-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25868-111">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="25868-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25868-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25868-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25868-113">См. также</span><span class="sxs-lookup"><span data-stu-id="25868-113">See also</span></span>

- [<span data-ttu-id="25868-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="25868-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="25868-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="25868-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
