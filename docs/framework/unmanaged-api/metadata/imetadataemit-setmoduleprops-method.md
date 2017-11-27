---
title: "Метод IMetaDataEmit::SetModuleProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetModuleProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0653f0407486e09ab51ef05e74218207268b6e8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="6bc10-102">Метод IMetaDataEmit::SetModuleProps</span><span class="sxs-lookup"><span data-stu-id="6bc10-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="6bc10-103">Обновляет ссылки на модуль, определяются в предыдущем вызове [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="6bc10-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bc10-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6bc10-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bc10-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6bc10-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="6bc10-106">[in] Имя модуля в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="6bc10-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="6bc10-107">Это только имя файла, а не полное имя пути.</span><span class="sxs-lookup"><span data-stu-id="6bc10-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bc10-108">Требования</span><span class="sxs-lookup"><span data-stu-id="6bc10-108">Requirements</span></span>  
 <span data-ttu-id="6bc10-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bc10-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bc10-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6bc10-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6bc10-111">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6bc10-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6bc10-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bc10-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bc10-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6bc10-113">See Also</span></span>  
 [<span data-ttu-id="6bc10-114">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6bc10-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="6bc10-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="6bc10-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
