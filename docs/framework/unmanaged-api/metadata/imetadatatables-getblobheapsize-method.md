---
title: Метод IMetaDataTables::GetBlobHeapSize
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
ms.openlocfilehash: c32407c3fc0bc5a045b80ec48937699826d981af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177162"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="38e54-102">Метод IMetaDataTables::GetBlobHeapSize</span><span class="sxs-lookup"><span data-stu-id="38e54-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="38e54-103">Получает размер, в байтах, двоичной большой объект (BLOB) кучи.</span><span class="sxs-lookup"><span data-stu-id="38e54-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38e54-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38e54-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="38e54-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="38e54-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="38e54-106">(ваут) Указатель на размер, в байтах, кучи BLOB.</span><span class="sxs-lookup"><span data-stu-id="38e54-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38e54-107">Требования</span><span class="sxs-lookup"><span data-stu-id="38e54-107">Requirements</span></span>  
 <span data-ttu-id="38e54-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38e54-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38e54-109">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="38e54-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38e54-110">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38e54-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38e54-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38e54-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38e54-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="38e54-112">See also</span></span>

- [<span data-ttu-id="38e54-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="38e54-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="38e54-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="38e54-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
