---
title: "Метод IMetaDataTables::GetGuidHeapSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetGuidHeapSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 76a2aa4495a9f34a57c8a84ec40ab946abc64532
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="2a140-102">Метод IMetaDataTables::GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="2a140-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="2a140-103">Возвращает размер в байтах, кучи GUID.</span><span class="sxs-lookup"><span data-stu-id="2a140-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a140-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a140-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a140-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a140-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="2a140-106">[out] Указатель на размер в байтах, кучи GUID.</span><span class="sxs-lookup"><span data-stu-id="2a140-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a140-107">Требования</span><span class="sxs-lookup"><span data-stu-id="2a140-107">Requirements</span></span>  
 <span data-ttu-id="2a140-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a140-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a140-109">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2a140-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a140-110">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a140-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a140-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a140-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a140-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2a140-112">See Also</span></span>  
 [<span data-ttu-id="2a140-113">IMetaDataTables-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2a140-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="2a140-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="2a140-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
