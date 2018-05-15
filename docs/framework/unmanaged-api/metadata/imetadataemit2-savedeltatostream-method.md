---
title: Метод IMetaDataEmit2::SaveDeltaToStream
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9dfd97ce5b9b192b9a2e88e3d7e4f963d929f47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="e669a-102">Метод IMetaDataEmit2::SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="e669a-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="e669a-103">Сохраняет изменения в текущем сеансе edit and continue в указанный поток.</span><span class="sxs-lookup"><span data-stu-id="e669a-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e669a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e669a-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e669a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e669a-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="e669a-106">[in] Указатель интерфейса, доступный для записи поток, в котором следует сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="e669a-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="e669a-107">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="e669a-107">[in] Reserved.</span></span> <span data-ttu-id="e669a-108">Это значение должно равняться нулю.</span><span class="sxs-lookup"><span data-stu-id="e669a-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e669a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e669a-109">Requirements</span></span>  
 <span data-ttu-id="e669a-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e669a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e669a-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e669a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e669a-112">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e669a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e669a-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e669a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e669a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e669a-114">See Also</span></span>  
 [<span data-ttu-id="e669a-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e669a-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="e669a-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e669a-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
