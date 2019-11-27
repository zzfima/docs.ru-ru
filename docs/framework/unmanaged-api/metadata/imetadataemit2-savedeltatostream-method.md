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
ms.openlocfilehash: b5da781f148c23efcc909ad65e198e4f3c6fe5b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447882"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="4f761-102">Метод IMetaDataEmit2::SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="4f761-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="4f761-103">Сохраняет изменения из текущего сеанса "изменить и продолжить" в указанный поток.</span><span class="sxs-lookup"><span data-stu-id="4f761-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f761-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f761-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f761-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f761-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="4f761-106">окне Указатель интерфейса на поток, доступный для записи, в который необходимо сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="4f761-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="4f761-107">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="4f761-107">[in] Reserved.</span></span> <span data-ttu-id="4f761-108">Это значение должно быть равно нулю.</span><span class="sxs-lookup"><span data-stu-id="4f761-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f761-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4f761-109">Requirements</span></span>  
 <span data-ttu-id="4f761-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f761-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f761-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="4f761-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f761-112">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4f761-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f761-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f761-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f761-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4f761-114">See also</span></span>

- [<span data-ttu-id="4f761-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="4f761-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="4f761-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="4f761-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
