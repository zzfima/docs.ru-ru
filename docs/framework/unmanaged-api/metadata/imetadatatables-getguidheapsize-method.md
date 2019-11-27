---
title: Метод IMetaDataTables::GetGuidHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuidHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type:
- apiref
ms.openlocfilehash: cf455b3fb34d8eed78ffaadffad621062c2b9b22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443493"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="e3dd0-102">Метод IMetaDataTables::GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="e3dd0-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="e3dd0-103">Возвращает размер кучи GUID в байтах.</span><span class="sxs-lookup"><span data-stu-id="e3dd0-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3dd0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3dd0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3dd0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3dd0-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="e3dd0-106">заполняет Указатель на размер кучи GUID в байтах.</span><span class="sxs-lookup"><span data-stu-id="e3dd0-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3dd0-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e3dd0-107">Requirements</span></span>  
 <span data-ttu-id="e3dd0-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3dd0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3dd0-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e3dd0-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e3dd0-110">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e3dd0-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e3dd0-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3dd0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3dd0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e3dd0-112">See also</span></span>

- [<span data-ttu-id="e3dd0-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="e3dd0-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="e3dd0-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="e3dd0-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
