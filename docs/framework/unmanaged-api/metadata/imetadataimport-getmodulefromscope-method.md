---
title: "Метод IMetaDataImport::GetModuleFromScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetModuleFromScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d7a9987f9a557cda79483e46c1798d471aa13944
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="7be9d-102">Метод IMetaDataImport::GetModuleFromScope</span><span class="sxs-lookup"><span data-stu-id="7be9d-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="7be9d-103">Получает маркер метаданных для модуля, ссылка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="7be9d-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be9d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7be9d-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7be9d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7be9d-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="7be9d-106">[out] Указатель на токен, представляющий модуль, указанный в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="7be9d-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7be9d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="7be9d-107">Requirements</span></span>  
 <span data-ttu-id="7be9d-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7be9d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7be9d-109">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7be9d-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7be9d-110">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7be9d-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7be9d-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7be9d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be9d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7be9d-112">See Also</span></span>  
 [<span data-ttu-id="7be9d-113">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="7be9d-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="7be9d-114">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="7be9d-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
