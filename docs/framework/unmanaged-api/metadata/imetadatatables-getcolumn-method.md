---
title: "Метод IMetaDataTables::GetColumn"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 162162b972ab0e1f3de55d56c18372f2475c9846
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="89d6b-102">Метод IMetaDataTables::GetColumn</span><span class="sxs-lookup"><span data-stu-id="89d6b-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="89d6b-103">Возвращает указатель на значение, содержащееся в ячейке указанного столбца и строки в данной таблице.</span><span class="sxs-lookup"><span data-stu-id="89d6b-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89d6b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89d6b-104">Syntax</span></span>  
  
```  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89d6b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="89d6b-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="89d6b-106">[in] Индекс таблицы.</span><span class="sxs-lookup"><span data-stu-id="89d6b-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="89d6b-107">[in] Индекс столбца в таблице.</span><span class="sxs-lookup"><span data-stu-id="89d6b-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="89d6b-108">[in] Индекс строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="89d6b-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="89d6b-109">[out] Указатель на значение в ячейке.</span><span class="sxs-lookup"><span data-stu-id="89d6b-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89d6b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="89d6b-110">Requirements</span></span>  
 <span data-ttu-id="89d6b-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89d6b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89d6b-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="89d6b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89d6b-113">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89d6b-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89d6b-114">**Версии платформы .NET framework**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89d6b-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d6b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="89d6b-115">See Also</span></span>  
 [<span data-ttu-id="89d6b-116">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="89d6b-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="89d6b-117">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="89d6b-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
