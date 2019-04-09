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
ms.openlocfilehash: 31bed2019eef5a37e1086624afdae3e8f2c58632
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119214"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="0b63e-102">Метод IMetaDataEmit2::SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="0b63e-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="0b63e-103">Сохраняет изменения в текущем сеансе, изменить и продолжить в указанный поток.</span><span class="sxs-lookup"><span data-stu-id="0b63e-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b63e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b63e-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b63e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b63e-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="0b63e-106">[in] Указатель интерфейса на доступный для записи поток, в котором следует сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="0b63e-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="0b63e-107">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="0b63e-107">[in] Reserved.</span></span> <span data-ttu-id="0b63e-108">Это значение должно равняться нулю.</span><span class="sxs-lookup"><span data-stu-id="0b63e-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b63e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0b63e-109">Requirements</span></span>  
 <span data-ttu-id="0b63e-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b63e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b63e-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0b63e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0b63e-112">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b63e-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="0b63e-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0b63e-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0b63e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0b63e-114">See also</span></span>

- [<span data-ttu-id="0b63e-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="0b63e-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="0b63e-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="0b63e-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
