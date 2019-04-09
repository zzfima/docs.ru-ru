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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f6b5582b96dfc83eed482def2c4c4abfeb33a4c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207790"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="73191-102">Метод IMetaDataEmit::SaveToStream</span><span class="sxs-lookup"><span data-stu-id="73191-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="73191-103">Сохраняет все метаданные в текущей области в указанном `IStream`.</span><span class="sxs-lookup"><span data-stu-id="73191-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73191-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73191-104">Syntax</span></span>  
  
```  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73191-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="73191-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="73191-106">[in] Доступный для записи поток для сохранения.</span><span class="sxs-lookup"><span data-stu-id="73191-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="73191-107">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="73191-107">[in] Reserved.</span></span> <span data-ttu-id="73191-108">Должен равняться нулю.</span><span class="sxs-lookup"><span data-stu-id="73191-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73191-109">Требования</span><span class="sxs-lookup"><span data-stu-id="73191-109">Requirements</span></span>  
 <span data-ttu-id="73191-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73191-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73191-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="73191-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73191-112">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73191-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="73191-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="73191-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="73191-114">См. также</span><span class="sxs-lookup"><span data-stu-id="73191-114">See also</span></span>

- [<span data-ttu-id="73191-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="73191-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="73191-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="73191-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
