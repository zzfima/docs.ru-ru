---
title: Метод IMetaDataTables::GetStringHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
ms.openlocfilehash: 43599a7e39ca4cc9d27dab43a948dc2f04e5010a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426670"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="7bf05-102">Метод IMetaDataTables::GetStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="7bf05-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="7bf05-103">Возвращает размер кучи строк (в байтах).</span><span class="sxs-lookup"><span data-stu-id="7bf05-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bf05-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bf05-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bf05-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7bf05-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="7bf05-106">заполняет Указатель на размер (в байтах) кучи строк.</span><span class="sxs-lookup"><span data-stu-id="7bf05-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bf05-107">Требования</span><span class="sxs-lookup"><span data-stu-id="7bf05-107">Requirements</span></span>  
 <span data-ttu-id="7bf05-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bf05-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bf05-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="7bf05-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7bf05-110">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7bf05-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7bf05-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bf05-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bf05-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7bf05-112">See also</span></span>

- [<span data-ttu-id="7bf05-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="7bf05-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="7bf05-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="7bf05-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
