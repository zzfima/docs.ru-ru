---
title: Функция GetRealProcAddress
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6826ee1b94f9a1c48c19150271ebc84ac54dda25
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471788"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="da766-102">Функция GetRealProcAddress</span><span class="sxs-lookup"><span data-stu-id="da766-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="da766-103">Получает адрес заданной функции, экспортируемой из последней установленной версии общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="da766-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="da766-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da766-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da766-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da766-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da766-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="da766-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="da766-107">[in] Имя функции.</span><span class="sxs-lookup"><span data-stu-id="da766-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="da766-108">[out] Расположение, которая получает указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="da766-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da766-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="da766-109">Return Value</span></span>  
 <span data-ttu-id="da766-110">Этот метод возвращает стандартные коды ошибок объектов модели компонентов (COM), как определено в файле WinError.h, помимо следующих значений, определенных в CorError.h.</span><span class="sxs-lookup"><span data-stu-id="da766-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="da766-111">Код возврата</span><span class="sxs-lookup"><span data-stu-id="da766-111">Return code</span></span>|<span data-ttu-id="da766-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="da766-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="da766-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="da766-113">S_OK</span></span>|<span data-ttu-id="da766-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="da766-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="da766-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="da766-115">E_POINTER</span></span>|<span data-ttu-id="da766-116">Недопустимый параметр `ppv`.</span><span class="sxs-lookup"><span data-stu-id="da766-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="da766-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="da766-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="da766-118">Функция не экспортируется из среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="da766-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da766-119">Требования</span><span class="sxs-lookup"><span data-stu-id="da766-119">Requirements</span></span>  
 <span data-ttu-id="da766-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da766-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da766-121">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="da766-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da766-122">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da766-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da766-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da766-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da766-124">См. также</span><span class="sxs-lookup"><span data-stu-id="da766-124">See also</span></span>
- [<span data-ttu-id="da766-125">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="da766-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
