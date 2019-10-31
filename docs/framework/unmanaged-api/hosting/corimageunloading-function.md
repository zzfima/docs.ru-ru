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
ms.openlocfilehash: 30e3a88140c8a438001e8428df4c5ee879c83376
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136923"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="da856-102">Функция _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="da856-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="da856-103">Уведомляет загрузчик об выгрузке образов управляемого модуля.</span><span class="sxs-lookup"><span data-stu-id="da856-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="da856-104">Эта функция не реализована.</span><span class="sxs-lookup"><span data-stu-id="da856-104">This function is not implemented.</span></span> <span data-ttu-id="da856-105">При вызове возвращается значение E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="da856-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da856-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da856-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da856-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="da856-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="da856-108">окне Указатель на начальное расположение изображения для выгрузки.</span><span class="sxs-lookup"><span data-stu-id="da856-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da856-109">Требования</span><span class="sxs-lookup"><span data-stu-id="da856-109">Requirements</span></span>  
 <span data-ttu-id="da856-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da856-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da856-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="da856-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da856-112">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="da856-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="da856-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da856-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da856-114">См. также</span><span class="sxs-lookup"><span data-stu-id="da856-114">See also</span></span>

- [<span data-ttu-id="da856-115">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="da856-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
