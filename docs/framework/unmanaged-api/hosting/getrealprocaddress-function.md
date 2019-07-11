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
ms.openlocfilehash: 0027514392dfbb93ab4189eb7c66a380fb77c1ae
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778156"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="65e92-102">Функция GetRealProcAddress</span><span class="sxs-lookup"><span data-stu-id="65e92-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="65e92-103">Получает адрес заданной функции, экспортируемой из последней установленной версии общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="65e92-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="65e92-104">Эта функция является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="65e92-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65e92-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65e92-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65e92-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="65e92-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="65e92-107">[in] Имя функции.</span><span class="sxs-lookup"><span data-stu-id="65e92-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="65e92-108">[out] Расположение, которая получает указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="65e92-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65e92-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="65e92-109">Return Value</span></span>  
 <span data-ttu-id="65e92-110">Этот метод возвращает стандартные коды ошибок объектов модели компонентов (COM), как определено в файле WinError.h, помимо следующих значений, определенных в CorError.h.</span><span class="sxs-lookup"><span data-stu-id="65e92-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="65e92-111">Код возврата</span><span class="sxs-lookup"><span data-stu-id="65e92-111">Return code</span></span>|<span data-ttu-id="65e92-112">Описание</span><span class="sxs-lookup"><span data-stu-id="65e92-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="65e92-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="65e92-113">S_OK</span></span>|<span data-ttu-id="65e92-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="65e92-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="65e92-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="65e92-115">E_POINTER</span></span>|<span data-ttu-id="65e92-116">Недопустимый параметр `ppv`.</span><span class="sxs-lookup"><span data-stu-id="65e92-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="65e92-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="65e92-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="65e92-118">Функция не экспортируется из среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="65e92-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65e92-119">Требования</span><span class="sxs-lookup"><span data-stu-id="65e92-119">Requirements</span></span>  
 <span data-ttu-id="65e92-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65e92-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65e92-121">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="65e92-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65e92-122">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="65e92-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65e92-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65e92-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65e92-124">См. также</span><span class="sxs-lookup"><span data-stu-id="65e92-124">See also</span></span>

- [<span data-ttu-id="65e92-125">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="65e92-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
