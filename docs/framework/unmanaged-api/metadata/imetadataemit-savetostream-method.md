---
title: Метод IMetaDataEmit::SaveToStream
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
ms.openlocfilehash: 7db27670b72a5018a03d4614b69486f67bcef155
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175685"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="55301-102">Метод IMetaDataEmit::SaveToStream</span><span class="sxs-lookup"><span data-stu-id="55301-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="55301-103">Сохраняет все метаданные в текущем диапазоне к указанному. `IStream`</span><span class="sxs-lookup"><span data-stu-id="55301-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55301-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55301-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55301-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55301-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="55301-106">(в) Порядок потока, чтобы сохранить.</span><span class="sxs-lookup"><span data-stu-id="55301-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="55301-107">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="55301-107">[in] Reserved.</span></span> <span data-ttu-id="55301-108">Должен равняться нулю.</span><span class="sxs-lookup"><span data-stu-id="55301-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55301-109">Требования</span><span class="sxs-lookup"><span data-stu-id="55301-109">Requirements</span></span>  
 <span data-ttu-id="55301-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55301-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55301-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="55301-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="55301-112">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55301-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55301-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55301-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55301-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="55301-114">See also</span></span>

- [<span data-ttu-id="55301-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="55301-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="55301-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="55301-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
