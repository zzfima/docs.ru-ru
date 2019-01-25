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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f6f16ebe57be0d09e97fe8aa95df892c2b02394
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696260"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="a7ff3-102">Метод IMetaDataTables::GetStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="a7ff3-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="a7ff3-103">Возвращает размер в байтах, кучи строк.</span><span class="sxs-lookup"><span data-stu-id="a7ff3-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ff3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7ff3-104">Syntax</span></span>  
  
```  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7ff3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7ff3-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="a7ff3-106">[out] Указатель на размер в байтах, кучи строк.</span><span class="sxs-lookup"><span data-stu-id="a7ff3-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7ff3-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a7ff3-107">Requirements</span></span>  
 <span data-ttu-id="a7ff3-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7ff3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7ff3-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a7ff3-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7ff3-110">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7ff3-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7ff3-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7ff3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ff3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a7ff3-112">See also</span></span>
- [<span data-ttu-id="a7ff3-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="a7ff3-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="a7ff3-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="a7ff3-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
