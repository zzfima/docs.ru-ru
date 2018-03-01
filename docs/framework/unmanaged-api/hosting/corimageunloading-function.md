---
title: "Функция _CorImageUnloading"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- _CorImageUnloading
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorImageUnloading
helpviewer_keywords:
- _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f0c105e84d34e83320d6c7d159a94ba4148b302
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corimageunloading-function"></a><span data-ttu-id="da107-102">Функция _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="da107-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="da107-103">Уведомляет загрузчика при выгрузке образов управляемых модулей.</span><span class="sxs-lookup"><span data-stu-id="da107-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="da107-104">Эта функция не реализована.</span><span class="sxs-lookup"><span data-stu-id="da107-104">This function is not implemented.</span></span> <span data-ttu-id="da107-105">При вызове возвращает значение E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="da107-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da107-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da107-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da107-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="da107-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="da107-108">[in] Указатель начальной позиции образа для выгрузки.</span><span class="sxs-lookup"><span data-stu-id="da107-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da107-109">Требования</span><span class="sxs-lookup"><span data-stu-id="da107-109">Requirements</span></span>  
 <span data-ttu-id="da107-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da107-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da107-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="da107-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da107-112">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da107-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="da107-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da107-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da107-114">См. также</span><span class="sxs-lookup"><span data-stu-id="da107-114">See Also</span></span>  
 [<span data-ttu-id="da107-115">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="da107-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
