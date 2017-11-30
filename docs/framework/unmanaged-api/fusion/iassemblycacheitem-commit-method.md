---
title: "Метод IAssemblyCacheItem::Commit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCacheItem.Commit
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a5a25f24fd1f09ebc1cda0442e41fde9eef059d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="d63ab-102">Метод IAssemblyCacheItem::Commit</span><span class="sxs-lookup"><span data-stu-id="d63ab-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="d63ab-103">Фиксирует ссылку на сборку, кэшированных в памяти.</span><span class="sxs-lookup"><span data-stu-id="d63ab-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d63ab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d63ab-104">Syntax</span></span>  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d63ab-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d63ab-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="d63ab-106">[in] Флаги, определенные в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="d63ab-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="d63ab-107">[out, optional] Значение, указывающее результат операции.</span><span class="sxs-lookup"><span data-stu-id="d63ab-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d63ab-108">Требования</span><span class="sxs-lookup"><span data-stu-id="d63ab-108">Requirements</span></span>  
 <span data-ttu-id="d63ab-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d63ab-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d63ab-110">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d63ab-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d63ab-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d63ab-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d63ab-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d63ab-112">See Also</span></span>  
 [<span data-ttu-id="d63ab-113">IAssemblyCacheItem-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d63ab-113">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
