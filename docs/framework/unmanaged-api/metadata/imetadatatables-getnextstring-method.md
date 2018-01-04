---
title: "Метод IMetaDataTables::GetNextString"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNextString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2bf16f6debd50729a95a4e887a01c1158b7a937
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="a7b0e-102">Метод IMetaDataTables::GetNextString</span><span class="sxs-lookup"><span data-stu-id="a7b0e-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="a7b0e-103">Возвращает индекс следующей строки в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="a7b0e-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7b0e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7b0e-104">Syntax</span></span>  
  
```  
HRESULT GetNextString (   
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7b0e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7b0e-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="a7b0e-106">[in] Значение индекса из столбца строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="a7b0e-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="a7b0e-107">[out] Указатель на индекс следующей строки в столбце.</span><span class="sxs-lookup"><span data-stu-id="a7b0e-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7b0e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="a7b0e-108">Requirements</span></span>  
 <span data-ttu-id="a7b0e-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7b0e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7b0e-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a7b0e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7b0e-111">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7b0e-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7b0e-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7b0e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7b0e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a7b0e-113">See Also</span></span>  
 [<span data-ttu-id="a7b0e-114">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="a7b0e-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="a7b0e-115">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="a7b0e-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
