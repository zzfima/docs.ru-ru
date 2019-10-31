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
ms.openlocfilehash: e661bd82ecf6d804e852cca4a4478084edf303c5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141499"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="3fe56-102">Функция RunDll32ShimW</span><span class="sxs-lookup"><span data-stu-id="3fe56-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="3fe56-103">Выполняет указанную команду.</span><span class="sxs-lookup"><span data-stu-id="3fe56-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="3fe56-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3fe56-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fe56-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3fe56-105">Syntax</span></span>  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fe56-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3fe56-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="3fe56-107">окне Маркер окна, в котором будут отображаться выходные данные команды.</span><span class="sxs-lookup"><span data-stu-id="3fe56-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="3fe56-108">окне Маркер библиотеки, которая содержит команду.</span><span class="sxs-lookup"><span data-stu-id="3fe56-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="3fe56-109">окне Строка, указывающая выполняемую команду.</span><span class="sxs-lookup"><span data-stu-id="3fe56-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="3fe56-110">окне Целое число, указывающее режим просмотра для окна вывода.</span><span class="sxs-lookup"><span data-stu-id="3fe56-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fe56-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3fe56-111">Requirements</span></span>  
 <span data-ttu-id="3fe56-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fe56-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fe56-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3fe56-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fe56-114">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3fe56-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fe56-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fe56-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fe56-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3fe56-116">See also</span></span>

- [<span data-ttu-id="3fe56-117">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="3fe56-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
