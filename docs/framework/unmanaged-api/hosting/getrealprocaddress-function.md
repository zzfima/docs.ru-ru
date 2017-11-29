---
title: "Функция GetRealProcAddress"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRealProcAddress
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetRealProcAddress
helpviewer_keywords: GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 53e51bcf72f1a59f5c471564022d0d8c415381a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="da7da-102">Функция GetRealProcAddress</span><span class="sxs-lookup"><span data-stu-id="da7da-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="da7da-103">Получает адрес указанной функции, экспортированные из последней установленной версии среды common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="da7da-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="da7da-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da7da-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da7da-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da7da-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da7da-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="da7da-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="da7da-107">[in] Имя функции.</span><span class="sxs-lookup"><span data-stu-id="da7da-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="da7da-108">[out] Расположение, получает указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="da7da-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da7da-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="da7da-109">Return Value</span></span>  
 <span data-ttu-id="da7da-110">Этот метод возвращает стандартные коды ошибок модели объектов компонентов (COM), как определено в файле WinError.h, кроме следующих значений, определенных в CorError.h.</span><span class="sxs-lookup"><span data-stu-id="da7da-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="da7da-111">Код возврата</span><span class="sxs-lookup"><span data-stu-id="da7da-111">Return code</span></span>|<span data-ttu-id="da7da-112">Описание</span><span class="sxs-lookup"><span data-stu-id="da7da-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="da7da-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="da7da-113">S_OK</span></span>|<span data-ttu-id="da7da-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="da7da-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="da7da-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="da7da-115">E_POINTER</span></span>|<span data-ttu-id="da7da-116">Недопустимый параметр `ppv`.</span><span class="sxs-lookup"><span data-stu-id="da7da-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="da7da-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="da7da-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="da7da-118">Функция не экспортируется из среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="da7da-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da7da-119">Требования</span><span class="sxs-lookup"><span data-stu-id="da7da-119">Requirements</span></span>  
 <span data-ttu-id="da7da-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da7da-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da7da-121">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="da7da-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da7da-122">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da7da-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da7da-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da7da-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da7da-124">См. также</span><span class="sxs-lookup"><span data-stu-id="da7da-124">See Also</span></span>  
 [<span data-ttu-id="da7da-125">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="da7da-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
