---
title: Метод IMetaDataTables::GetGuidHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuidHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 812794bc76d475c516effdc950ca6a0b877494c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178364"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="de20e-102">Метод IMetaDataTables::GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="de20e-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="de20e-103">Возвращает размер в байтах, кучи GUID.</span><span class="sxs-lookup"><span data-stu-id="de20e-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de20e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de20e-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de20e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="de20e-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="de20e-106">[out] Указатель на размер в байтах, кучи GUID.</span><span class="sxs-lookup"><span data-stu-id="de20e-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de20e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="de20e-107">Requirements</span></span>  
 <span data-ttu-id="de20e-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de20e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de20e-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="de20e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de20e-110">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="de20e-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="de20e-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de20e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de20e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="de20e-112">See also</span></span>

- [<span data-ttu-id="de20e-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="de20e-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="de20e-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="de20e-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
