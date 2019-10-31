---
title: Функция CallFunctionShim
ms.date: 03/30/2017
api_name:
- CallFunctionShim
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CallFunctionShim
helpviewer_keywords:
- CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type:
- apiref
ms.openlocfilehash: d39e15a2ba71ba0c0147482259f5618dcb5d298b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192098"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="f714a-102">Функция CallFunctionShim</span><span class="sxs-lookup"><span data-stu-id="f714a-102">CallFunctionShim Function</span></span>
<span data-ttu-id="f714a-103">Вызывает функцию с указанным именем и параметрами в указанной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="f714a-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="f714a-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f714a-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f714a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f714a-105">Syntax</span></span>  
  
```cpp  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f714a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f714a-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="f714a-107">окне Имя библиотеки, содержащей функцию.</span><span class="sxs-lookup"><span data-stu-id="f714a-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="f714a-108">окне Имя функции.</span><span class="sxs-lookup"><span data-stu-id="f714a-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="f714a-109">окне Первый аргумент для передачи в функцию.</span><span class="sxs-lookup"><span data-stu-id="f714a-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="f714a-110">окне Второй аргумент для передачи в функцию.</span><span class="sxs-lookup"><span data-stu-id="f714a-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="f714a-111">окне Версия библиотеки, которая содержит функцию.</span><span class="sxs-lookup"><span data-stu-id="f714a-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="f714a-112">окне Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="f714a-112">[in] Reserved for future use.</span></span> <span data-ttu-id="f714a-113">В этом параметре следует передать ноль.</span><span class="sxs-lookup"><span data-stu-id="f714a-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f714a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f714a-114">Requirements</span></span>  
 <span data-ttu-id="f714a-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f714a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f714a-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f714a-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f714a-117">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f714a-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f714a-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f714a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f714a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f714a-119">See also</span></span>

- [<span data-ttu-id="f714a-120">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="f714a-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
