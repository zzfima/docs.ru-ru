---
title: Метод IMetaDataTables::GetNextBlob
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b8a91a2c1ef9b68dcfc293a870ce3e9b9499a8f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204605"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="c1376-102">Метод IMetaDataTables::GetNextBlob</span><span class="sxs-lookup"><span data-stu-id="c1376-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="c1376-103">Возвращает индекс следующей большой двоичный объект (BLOB) в таблице.</span><span class="sxs-lookup"><span data-stu-id="c1376-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1376-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1376-104">Syntax</span></span>  
  
```  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1376-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1376-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="c1376-106">[in] Индекс, возвращенный столбец больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="c1376-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="c1376-107">[out] Указатель на индекс следующий большой двоичный объект.</span><span class="sxs-lookup"><span data-stu-id="c1376-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1376-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c1376-108">Requirements</span></span>  
 <span data-ttu-id="c1376-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1376-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1376-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c1376-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1376-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1376-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c1376-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1376-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1376-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c1376-113">See also</span></span>

- [<span data-ttu-id="c1376-114">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="c1376-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c1376-115">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="c1376-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
