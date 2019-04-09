---
title: Метод IMetaDataTables::GetBlobHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d22e61d28e0fbf06fa1cfe9e9ac18a534726f01d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076459"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="f680e-102">Метод IMetaDataTables::GetBlobHeapSize</span><span class="sxs-lookup"><span data-stu-id="f680e-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="f680e-103">Возвращает размер в байтах, кучи больших двоичных объектов (BLOB).</span><span class="sxs-lookup"><span data-stu-id="f680e-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f680e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f680e-104">Syntax</span></span>  
  
```  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="f680e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f680e-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="f680e-106">[out] Указатель на размер в байтах в куче больших двоичных ОБЪЕКТОВ.</span><span class="sxs-lookup"><span data-stu-id="f680e-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f680e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f680e-107">Requirements</span></span>  
 <span data-ttu-id="f680e-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f680e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f680e-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f680e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f680e-110">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f680e-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f680e-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f680e-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f680e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f680e-112">See also</span></span>

- [<span data-ttu-id="f680e-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="f680e-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="f680e-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="f680e-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
