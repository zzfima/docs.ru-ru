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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31d93ac427ec67726c9456d623aeb683c9029ccd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773765"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="8cb4a-102">Функция CallFunctionShim</span><span class="sxs-lookup"><span data-stu-id="8cb4a-102">CallFunctionShim Function</span></span>
<span data-ttu-id="8cb4a-103">Вызывает функцию, которая имеет указанные имя и параметры в указанной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="8cb4a-104">Эта функция является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cb4a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8cb4a-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8cb4a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8cb4a-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="8cb4a-107">[in] Имя библиотеки, содержащей функцию.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="8cb4a-108">[in] Имя функции.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="8cb4a-109">[in] Первый аргумент, передаваемый в функцию.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="8cb4a-110">[in] Второй аргумент, передаваемый в функцию.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="8cb4a-111">[in] Версия библиотеки, содержащей функцию.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="8cb4a-112">[in] Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-112">[in] Reserved for future use.</span></span> <span data-ttu-id="8cb4a-113">Передайте нулевое значение в этом параметре.</span><span class="sxs-lookup"><span data-stu-id="8cb4a-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cb4a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8cb4a-114">Requirements</span></span>  
 <span data-ttu-id="8cb4a-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cb4a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cb4a-116">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8cb4a-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8cb4a-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8cb4a-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8cb4a-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cb4a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cb4a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="8cb4a-119">See also</span></span>

- [<span data-ttu-id="8cb4a-120">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="8cb4a-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
