---
title: Метод IMetaDataEmit2::SaveDeltaToMemory
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fa95a737747e9153eb844cddd8e0684585b9108b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081149"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="66899-102">Метод IMetaDataEmit2::SaveDeltaToMemory</span><span class="sxs-lookup"><span data-stu-id="66899-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="66899-103">Сохраняет изменения в текущем сеансе, изменить и продолжить в памяти.</span><span class="sxs-lookup"><span data-stu-id="66899-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66899-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66899-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66899-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66899-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="66899-106">[out] Адрес, с которого начинается запись изменений метаданных.</span><span class="sxs-lookup"><span data-stu-id="66899-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="66899-107">[in] Размер изменения.</span><span class="sxs-lookup"><span data-stu-id="66899-107">[in] The size of the changes.</span></span> <span data-ttu-id="66899-108">Используйте [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) для определения размера.</span><span class="sxs-lookup"><span data-stu-id="66899-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66899-109">Требования</span><span class="sxs-lookup"><span data-stu-id="66899-109">Requirements</span></span>  
 <span data-ttu-id="66899-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66899-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66899-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="66899-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66899-112">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="66899-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="66899-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66899-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66899-114">См. также</span><span class="sxs-lookup"><span data-stu-id="66899-114">See also</span></span>

- [<span data-ttu-id="66899-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="66899-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="66899-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="66899-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
