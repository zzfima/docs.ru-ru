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
ms.openlocfilehash: 1060ca140db0304c8e5667f7fdf9624b3ac2b64a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="ecd56-102">Функция CallFunctionShim</span><span class="sxs-lookup"><span data-stu-id="ecd56-102">CallFunctionShim Function</span></span>
<span data-ttu-id="ecd56-103">Выполняется вызов функции с указанным именем и параметрами в указанной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="ecd56-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="ecd56-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecd56-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecd56-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecd56-105">Syntax</span></span>  
  
```  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecd56-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ecd56-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="ecd56-107">[in] Имя библиотеки, содержащего функцию.</span><span class="sxs-lookup"><span data-stu-id="ecd56-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="ecd56-108">[in] Имя функции.</span><span class="sxs-lookup"><span data-stu-id="ecd56-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="ecd56-109">[in] Первый аргумент, передаваемый в функцию.</span><span class="sxs-lookup"><span data-stu-id="ecd56-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="ecd56-110">[in] Второй аргумент, передаваемый в функцию.</span><span class="sxs-lookup"><span data-stu-id="ecd56-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="ecd56-111">[in] Версия библиотеки, содержащего функцию.</span><span class="sxs-lookup"><span data-stu-id="ecd56-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="ecd56-112">[in] Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="ecd56-112">[in] Reserved for future use.</span></span> <span data-ttu-id="ecd56-113">Передайте нулевое значение в этом параметре.</span><span class="sxs-lookup"><span data-stu-id="ecd56-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecd56-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ecd56-114">Requirements</span></span>  
 <span data-ttu-id="ecd56-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecd56-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecd56-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ecd56-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ecd56-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ecd56-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ecd56-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecd56-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecd56-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ecd56-119">See Also</span></span>  
 [<span data-ttu-id="ecd56-120">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="ecd56-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
