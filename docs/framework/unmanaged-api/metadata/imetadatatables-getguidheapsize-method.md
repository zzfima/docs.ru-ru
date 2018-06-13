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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97d196769b549022ce498958fc34cf08df442d0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447094"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="5100b-102">Метод IMetaDataTables::GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="5100b-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="5100b-103">Возвращает размер в байтах, кучи GUID.</span><span class="sxs-lookup"><span data-stu-id="5100b-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5100b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5100b-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5100b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5100b-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="5100b-106">[out] Указатель на размер в байтах, кучи GUID.</span><span class="sxs-lookup"><span data-stu-id="5100b-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5100b-107">Требования</span><span class="sxs-lookup"><span data-stu-id="5100b-107">Requirements</span></span>  
 <span data-ttu-id="5100b-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5100b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5100b-109">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5100b-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5100b-110">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5100b-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5100b-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5100b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5100b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="5100b-112">See Also</span></span>  
 [<span data-ttu-id="5100b-113">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="5100b-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="5100b-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="5100b-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
