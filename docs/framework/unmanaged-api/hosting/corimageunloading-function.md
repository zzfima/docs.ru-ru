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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086433"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="ffc21-102">Функция _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="ffc21-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="ffc21-103">Уведомляет загрузчик о выгрузке образов управляемого модуля.</span><span class="sxs-lookup"><span data-stu-id="ffc21-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="ffc21-104">Эта функция не реализована.</span><span class="sxs-lookup"><span data-stu-id="ffc21-104">This function is not implemented.</span></span> <span data-ttu-id="ffc21-105">При вызове, он возвращает E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="ffc21-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffc21-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffc21-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffc21-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ffc21-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="ffc21-108">[in] Указатель на начальное расположение образа для выгрузки.</span><span class="sxs-lookup"><span data-stu-id="ffc21-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffc21-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ffc21-109">Requirements</span></span>  
 <span data-ttu-id="ffc21-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffc21-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffc21-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ffc21-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ffc21-112">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ffc21-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ffc21-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffc21-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffc21-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ffc21-114">See also</span></span>

- [<span data-ttu-id="ffc21-115">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="ffc21-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
