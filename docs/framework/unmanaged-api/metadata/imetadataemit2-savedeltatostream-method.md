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
ms.openlocfilehash: 270fdecb6afbf252b7d0531cab0f18dded44298d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777121"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="d7236-102">Метод IMetaDataEmit2::SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="d7236-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="d7236-103">Сохраняет изменения в текущем сеансе, изменить и продолжить в указанный поток.</span><span class="sxs-lookup"><span data-stu-id="d7236-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7236-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7236-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7236-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7236-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="d7236-106">[in] Указатель интерфейса на доступный для записи поток, в котором следует сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="d7236-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="d7236-107">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="d7236-107">[in] Reserved.</span></span> <span data-ttu-id="d7236-108">Это значение должно равняться нулю.</span><span class="sxs-lookup"><span data-stu-id="d7236-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7236-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d7236-109">Requirements</span></span>  
 <span data-ttu-id="d7236-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7236-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7236-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d7236-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7236-112">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d7236-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7236-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7236-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7236-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d7236-114">See also</span></span>

- [<span data-ttu-id="d7236-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="d7236-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="d7236-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="d7236-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
