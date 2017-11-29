---
title: "Функция _CorImageUnloading"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorImageUnloading
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorImageUnloading
helpviewer_keywords: _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90df58e2765cdecf4a1ec22cf5540e5cfa9530a9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corimageunloading-function"></a><span data-ttu-id="39b6b-102">Функция _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="39b6b-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="39b6b-103">Уведомляет загрузчика при выгрузке образов управляемых модулей.</span><span class="sxs-lookup"><span data-stu-id="39b6b-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="39b6b-104">Эта функция не реализована.</span><span class="sxs-lookup"><span data-stu-id="39b6b-104">This function is not implemented.</span></span> <span data-ttu-id="39b6b-105">При вызове возвращает значение E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="39b6b-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39b6b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39b6b-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39b6b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="39b6b-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="39b6b-108">[in] Указатель начальной позиции образа для выгрузки.</span><span class="sxs-lookup"><span data-stu-id="39b6b-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39b6b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="39b6b-109">Requirements</span></span>  
 <span data-ttu-id="39b6b-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39b6b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39b6b-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="39b6b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39b6b-112">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="39b6b-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="39b6b-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39b6b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39b6b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="39b6b-114">See Also</span></span>  
 [<span data-ttu-id="39b6b-115">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="39b6b-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
