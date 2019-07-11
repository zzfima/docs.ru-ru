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
ms.openlocfilehash: b1e7181f50d94fa417bf9d00c3531747cefca82c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781478"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="b12ac-102">Метод IMetaDataTables::GetNextBlob</span><span class="sxs-lookup"><span data-stu-id="b12ac-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="b12ac-103">Возвращает индекс следующей большой двоичный объект (BLOB) в таблице.</span><span class="sxs-lookup"><span data-stu-id="b12ac-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b12ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b12ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b12ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b12ac-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="b12ac-106">[in] Индекс, возвращенный столбец больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="b12ac-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="b12ac-107">[out] Указатель на индекс следующий большой двоичный объект.</span><span class="sxs-lookup"><span data-stu-id="b12ac-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b12ac-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b12ac-108">Requirements</span></span>  
 <span data-ttu-id="b12ac-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b12ac-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b12ac-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b12ac-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b12ac-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b12ac-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b12ac-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b12ac-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b12ac-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b12ac-113">See also</span></span>

- [<span data-ttu-id="b12ac-114">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="b12ac-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="b12ac-115">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="b12ac-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
