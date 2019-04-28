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
ms.openlocfilehash: ccfdf9ffab35f076b85c067c2b412020a5f541b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765171"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="dc2fa-102">Функция RunDll32ShimW</span><span class="sxs-lookup"><span data-stu-id="dc2fa-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="dc2fa-103">Выполняет указанную команду.</span><span class="sxs-lookup"><span data-stu-id="dc2fa-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="dc2fa-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc2fa-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc2fa-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc2fa-105">Syntax</span></span>  
  
```  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc2fa-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="dc2fa-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="dc2fa-107">[in] Дескриптор окна, в которой будут отображаться выходные данные команды.</span><span class="sxs-lookup"><span data-stu-id="dc2fa-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="dc2fa-108">[in] Дескриптор в библиотеку, содержащую команду.</span><span class="sxs-lookup"><span data-stu-id="dc2fa-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="dc2fa-109">[in] Строковое значение, указывающее выполняемую команду.</span><span class="sxs-lookup"><span data-stu-id="dc2fa-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="dc2fa-110">[in] Целое число, указывающее режим отображения для окна вывода.</span><span class="sxs-lookup"><span data-stu-id="dc2fa-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc2fa-111">Требования</span><span class="sxs-lookup"><span data-stu-id="dc2fa-111">Requirements</span></span>  
 <span data-ttu-id="dc2fa-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc2fa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc2fa-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dc2fa-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc2fa-114">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dc2fa-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc2fa-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc2fa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc2fa-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dc2fa-116">See also</span></span>

- [<span data-ttu-id="dc2fa-117">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="dc2fa-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
