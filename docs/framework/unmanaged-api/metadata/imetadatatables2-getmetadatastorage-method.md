---
title: Метод IMetaDataTables2::GetMetaDataStorage
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStorage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f12243571262ad7511795c48721617932fc6b30b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59161412"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="cbb78-102">Метод IMetaDataTables2::GetMetaDataStorage</span><span class="sxs-lookup"><span data-stu-id="cbb78-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="cbb78-103">Получает размер и содержимое метаданных, хранящихся в указанном разделе.</span><span class="sxs-lookup"><span data-stu-id="cbb78-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbb78-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbb78-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbb78-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cbb78-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="cbb78-106">[in, out] Указатель на раздел метаданных.</span><span class="sxs-lookup"><span data-stu-id="cbb78-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="cbb78-107">[out] Размер потока метаданных.</span><span class="sxs-lookup"><span data-stu-id="cbb78-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbb78-108">Требования</span><span class="sxs-lookup"><span data-stu-id="cbb78-108">Requirements</span></span>  
 <span data-ttu-id="cbb78-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbb78-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbb78-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cbb78-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cbb78-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cbb78-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cbb78-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbb78-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbb78-113">См. также</span><span class="sxs-lookup"><span data-stu-id="cbb78-113">See also</span></span>

- [<span data-ttu-id="cbb78-114">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="cbb78-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="cbb78-115">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="cbb78-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
