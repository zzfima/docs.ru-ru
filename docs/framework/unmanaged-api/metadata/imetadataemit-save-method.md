---
title: "Метод IMetaDataEmit::Save"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.Save
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a11241894116f57889a15a184290cd95f2f4f54f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="262f2-102">Метод IMetaDataEmit::Save</span><span class="sxs-lookup"><span data-stu-id="262f2-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="262f2-103">Сохраняет все метаданные в текущей области в файле по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="262f2-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="262f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="262f2-104">Syntax</span></span>  
  
```  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="262f2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="262f2-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="262f2-106">[in] Имя файла для сохранения.</span><span class="sxs-lookup"><span data-stu-id="262f2-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="262f2-107">Если это значение равно null, в памяти копия будет сохранена до последнего расположение, которое было использовано.</span><span class="sxs-lookup"><span data-stu-id="262f2-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="262f2-108">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="262f2-108">[in] Reserved.</span></span> <span data-ttu-id="262f2-109">Должен равняться нулю.</span><span class="sxs-lookup"><span data-stu-id="262f2-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="262f2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="262f2-110">Requirements</span></span>  
 <span data-ttu-id="262f2-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="262f2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="262f2-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="262f2-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="262f2-113">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="262f2-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="262f2-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="262f2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="262f2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="262f2-115">See Also</span></span>  
 [<span data-ttu-id="262f2-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="262f2-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="262f2-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="262f2-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
