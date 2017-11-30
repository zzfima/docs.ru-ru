---
title: "Метод IMetaDataTables::GetBlobHeapSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetBlobHeapSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 796a7246a90f60627906b1febb6fbe15152ed8e8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="756b3-102">Метод IMetaDataTables::GetBlobHeapSize</span><span class="sxs-lookup"><span data-stu-id="756b3-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="756b3-103">Возвращает размер в байтах в куче больших двоичных объектов (BLOB).</span><span class="sxs-lookup"><span data-stu-id="756b3-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="756b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="756b3-104">Syntax</span></span>  
  
```  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="756b3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="756b3-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="756b3-106">[out] Указатель на размер в байтах в куче больших двоичных ОБЪЕКТОВ.</span><span class="sxs-lookup"><span data-stu-id="756b3-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="756b3-107">Требования</span><span class="sxs-lookup"><span data-stu-id="756b3-107">Requirements</span></span>  
 <span data-ttu-id="756b3-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="756b3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="756b3-109">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="756b3-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="756b3-110">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="756b3-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="756b3-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="756b3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="756b3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="756b3-112">See Also</span></span>  
 [<span data-ttu-id="756b3-113">IMetaDataTables-интерфейс</span><span class="sxs-lookup"><span data-stu-id="756b3-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="756b3-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="756b3-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
