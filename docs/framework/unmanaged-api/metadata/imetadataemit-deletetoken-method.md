---
title: Метод IMetaDataEmit::DeleteToken
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type:
- apiref
ms.openlocfilehash: e8c145632911817e8e19d587bb8afead0a6c33af
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434349"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="6a61f-102">Метод IMetaDataEmit::DeleteToken</span><span class="sxs-lookup"><span data-stu-id="6a61f-102">IMetaDataEmit::DeleteToken Method</span></span>
<span data-ttu-id="6a61f-103">Удаляет указанный токен из текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="6a61f-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a61f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a61f-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteToken (   
    [in]  mdToken     tkObj   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a61f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6a61f-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="6a61f-106">окне Удаляемый токен.</span><span class="sxs-lookup"><span data-stu-id="6a61f-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a61f-107">Требования</span><span class="sxs-lookup"><span data-stu-id="6a61f-107">Requirements</span></span>  
 <span data-ttu-id="6a61f-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a61f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a61f-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="6a61f-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a61f-110">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6a61f-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a61f-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a61f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a61f-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="6a61f-112">See also</span></span>

- [<span data-ttu-id="6a61f-113">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="6a61f-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6a61f-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="6a61f-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
