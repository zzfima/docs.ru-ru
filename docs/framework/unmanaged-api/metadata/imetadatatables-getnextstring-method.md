---
title: Метод IMetaDataTables::GetNextString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e7e7d89f4c994c5ce37dc09d15826185ed1bb25
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129380"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="d648d-102">Метод IMetaDataTables::GetNextString</span><span class="sxs-lookup"><span data-stu-id="d648d-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="d648d-103">Получает индекс следующей строки в текущем столбце таблицы.</span><span class="sxs-lookup"><span data-stu-id="d648d-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d648d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d648d-104">Syntax</span></span>  
  
```  
HRESULT GetNextString (   
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d648d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d648d-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="d648d-106">[in] Значение индекса из строкового столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="d648d-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="d648d-107">[out] Указатель на индекс следующей строки в столбце.</span><span class="sxs-lookup"><span data-stu-id="d648d-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d648d-108">Требования</span><span class="sxs-lookup"><span data-stu-id="d648d-108">Requirements</span></span>  
 <span data-ttu-id="d648d-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d648d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d648d-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d648d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d648d-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d648d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d648d-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d648d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d648d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="d648d-113">See also</span></span>

- [<span data-ttu-id="d648d-114">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="d648d-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="d648d-115">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="d648d-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
