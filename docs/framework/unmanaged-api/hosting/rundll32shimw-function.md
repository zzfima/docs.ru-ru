---
title: Функция RunDll32ShimW
ms.date: 03/30/2017
api_name:
- RunDll32ShimW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- RunDll32ShimW
helpviewer_keywords:
- RunDll32ShimW function [.NET Framework hosting]
ms.assetid: 9ea07b57-96e2-44df-8711-8fe6c119087f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa7df47ab55b8dc7ef3f55f5591b44614052bcee
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490136"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="6c637-102">Функция RunDll32ShimW</span><span class="sxs-lookup"><span data-stu-id="6c637-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="6c637-103">Выполняет указанную команду.</span><span class="sxs-lookup"><span data-stu-id="6c637-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="6c637-104">Эта функция является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="6c637-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c637-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c637-105">Syntax</span></span>  
  
```  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c637-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c637-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="6c637-107">[in] Дескриптор окна, в которой будут отображаться выходные данные команды.</span><span class="sxs-lookup"><span data-stu-id="6c637-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="6c637-108">[in] Дескриптор в библиотеку, содержащую команду.</span><span class="sxs-lookup"><span data-stu-id="6c637-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="6c637-109">[in] Строковое значение, указывающее выполняемую команду.</span><span class="sxs-lookup"><span data-stu-id="6c637-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="6c637-110">[in] Целое число, указывающее режим отображения для окна вывода.</span><span class="sxs-lookup"><span data-stu-id="6c637-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c637-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6c637-111">Requirements</span></span>  
 <span data-ttu-id="6c637-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c637-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c637-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6c637-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c637-114">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c637-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c637-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c637-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c637-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6c637-116">See also</span></span>

- [<span data-ttu-id="6c637-117">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="6c637-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
