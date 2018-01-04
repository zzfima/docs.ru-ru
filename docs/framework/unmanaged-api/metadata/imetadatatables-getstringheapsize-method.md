---
title: "Метод IMetaDataTables::GetStringHeapSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetStringHeapSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f7ff6d6296e36d8d1a55682b453941b932bd590
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="e30a6-102">Метод IMetaDataTables::GetStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="e30a6-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="e30a6-103">Возвращает размер в байтах, кучи строк.</span><span class="sxs-lookup"><span data-stu-id="e30a6-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e30a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e30a6-104">Syntax</span></span>  
  
```  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e30a6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e30a6-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="e30a6-106">[out] Указатель на размер в байтах, кучи строк.</span><span class="sxs-lookup"><span data-stu-id="e30a6-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e30a6-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e30a6-107">Requirements</span></span>  
 <span data-ttu-id="e30a6-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e30a6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e30a6-109">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e30a6-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e30a6-110">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e30a6-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e30a6-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e30a6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e30a6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e30a6-112">See Also</span></span>  
 [<span data-ttu-id="e30a6-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="e30a6-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="e30a6-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="e30a6-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
