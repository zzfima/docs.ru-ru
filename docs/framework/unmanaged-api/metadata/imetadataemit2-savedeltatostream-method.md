---
title: "Метод IMetaDataEmit2::SaveDeltaToStream"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bcfd90da200e04e5834b21ea84a3a84acc5b732d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="5f974-102">Метод IMetaDataEmit2::SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="5f974-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="5f974-103">Сохраняет изменения в текущем сеансе edit and continue в указанный поток.</span><span class="sxs-lookup"><span data-stu-id="5f974-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f974-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f974-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f974-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f974-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="5f974-106">[in] Указатель интерфейса, доступный для записи поток, в котором следует сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="5f974-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="5f974-107">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="5f974-107">[in] Reserved.</span></span> <span data-ttu-id="5f974-108">Это значение должно равняться нулю.</span><span class="sxs-lookup"><span data-stu-id="5f974-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f974-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5f974-109">Requirements</span></span>  
 <span data-ttu-id="5f974-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f974-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f974-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5f974-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f974-112">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f974-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f974-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f974-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f974-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5f974-114">See Also</span></span>  
 [<span data-ttu-id="5f974-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="5f974-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="5f974-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="5f974-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
