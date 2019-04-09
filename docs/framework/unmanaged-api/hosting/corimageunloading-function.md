---
title: Функция _CorImageUnloading
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cb5f9decbcdfb71f67a5132dc59773f1de8b0a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086433"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="d72d6-102">Функция _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="d72d6-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="d72d6-103">Уведомляет загрузчик о выгрузке образов управляемого модуля.</span><span class="sxs-lookup"><span data-stu-id="d72d6-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="d72d6-104">Эта функция не реализована.</span><span class="sxs-lookup"><span data-stu-id="d72d6-104">This function is not implemented.</span></span> <span data-ttu-id="d72d6-105">При вызове, он возвращает E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="d72d6-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d72d6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d72d6-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d72d6-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="d72d6-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="d72d6-108">[in] Указатель на начальное расположение образа для выгрузки.</span><span class="sxs-lookup"><span data-stu-id="d72d6-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d72d6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d72d6-109">Requirements</span></span>  
 <span data-ttu-id="d72d6-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d72d6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d72d6-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d72d6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d72d6-112">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d72d6-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="d72d6-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d72d6-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d72d6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d72d6-114">See also</span></span>

- [<span data-ttu-id="d72d6-115">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="d72d6-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
