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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d85fb62936678f830ca7eaf26a97c36be5f23ac8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138246"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="0540a-102">Метод IMetaDataEmit::DeleteToken</span><span class="sxs-lookup"><span data-stu-id="0540a-102">IMetaDataEmit::DeleteToken Method</span></span>
<span data-ttu-id="0540a-103">Удаляет указанный маркер из текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="0540a-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0540a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0540a-104">Syntax</span></span>  
  
```  
HRESULT DeleteToken (   
    [in]  mdToken     tkObj   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0540a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0540a-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="0540a-106">[in] Токен для удаления.</span><span class="sxs-lookup"><span data-stu-id="0540a-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0540a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="0540a-107">Requirements</span></span>  
 <span data-ttu-id="0540a-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0540a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0540a-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0540a-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0540a-110">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0540a-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0540a-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0540a-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0540a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0540a-112">See also</span></span>

- [<span data-ttu-id="0540a-113">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="0540a-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0540a-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="0540a-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
