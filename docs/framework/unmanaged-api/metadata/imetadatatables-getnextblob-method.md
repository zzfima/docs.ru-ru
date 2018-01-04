---
title: "Метод IMetaDataTables::GetNextBlob"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNextBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 399cf6626e7a56584829b2a8417958ce7e608727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="d2562-102">Метод IMetaDataTables::GetNextBlob</span><span class="sxs-lookup"><span data-stu-id="d2562-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="d2562-103">Возвращает индекс следующей большой двоичный объект (BLOB) в таблице.</span><span class="sxs-lookup"><span data-stu-id="d2562-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2562-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2562-104">Syntax</span></span>  
  
```  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2562-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d2562-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="d2562-106">[in] Индекс, возвращенный из столбцов больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="d2562-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="d2562-107">[out] Указатель на индекс следующего большого двоичного ОБЪЕКТА.</span><span class="sxs-lookup"><span data-stu-id="d2562-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2562-108">Требования</span><span class="sxs-lookup"><span data-stu-id="d2562-108">Requirements</span></span>  
 <span data-ttu-id="d2562-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2562-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2562-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d2562-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2562-111">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2562-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d2562-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2562-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2562-113">См. также</span><span class="sxs-lookup"><span data-stu-id="d2562-113">See Also</span></span>  
 [<span data-ttu-id="d2562-114">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="d2562-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="d2562-115">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="d2562-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
