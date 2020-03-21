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
ms.openlocfilehash: 4932e1fd6294f4a01264e982835dd0707324082a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178231"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="8ee8d-102">Функция _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="8ee8d-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="8ee8d-103">Уведомляет погрузчик при разгрузке управляемых изображений модуля.</span><span class="sxs-lookup"><span data-stu-id="8ee8d-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="8ee8d-104">Эта функция не реализована.</span><span class="sxs-lookup"><span data-stu-id="8ee8d-104">This function is not implemented.</span></span> <span data-ttu-id="8ee8d-105">Если вызов, он возвращает E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="8ee8d-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ee8d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ee8d-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ee8d-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="8ee8d-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="8ee8d-108">(в) Указатель на исходное местоположение изображения для разгрузки.</span><span class="sxs-lookup"><span data-stu-id="8ee8d-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ee8d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8ee8d-109">Requirements</span></span>  
 <span data-ttu-id="8ee8d-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ee8d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ee8d-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8ee8d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ee8d-112">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8ee8d-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ee8d-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ee8d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee8d-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8ee8d-114">See also</span></span>

- [<span data-ttu-id="8ee8d-115">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="8ee8d-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
