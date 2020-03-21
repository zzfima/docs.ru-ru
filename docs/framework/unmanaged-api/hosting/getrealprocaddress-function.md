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
ms.openlocfilehash: 4c914e00987053b1c1e9e00bf8e54632175e1de8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178163"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="4eba7-102">Функция GetRealProcAddress</span><span class="sxs-lookup"><span data-stu-id="4eba7-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="4eba7-103">Получает адрес указанной функции, которая экспортируется из последней установленной версии общего времени выполнения языка (CLR).</span><span class="sxs-lookup"><span data-stu-id="4eba7-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="4eba7-104">Эта функция была унесена в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="4eba7-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4eba7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4eba7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4eba7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4eba7-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="4eba7-107">(в) Название функции.</span><span class="sxs-lookup"><span data-stu-id="4eba7-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="4eba7-108">(ваут) Местоположение, которое получает указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="4eba7-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4eba7-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4eba7-109">Return Value</span></span>  
 <span data-ttu-id="4eba7-110">Этот метод возвращает стандартные коды ошибок компонентной модели объектов (COM), как это определено в WinError.h, в дополнение к следующим значениям, определенным в CorError.h.</span><span class="sxs-lookup"><span data-stu-id="4eba7-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="4eba7-111">Код возврата</span><span class="sxs-lookup"><span data-stu-id="4eba7-111">Return code</span></span>|<span data-ttu-id="4eba7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4eba7-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="4eba7-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="4eba7-113">S_OK</span></span>|<span data-ttu-id="4eba7-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="4eba7-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="4eba7-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="4eba7-115">E_POINTER</span></span>|<span data-ttu-id="4eba7-116">Недопустимый параметр `ppv`.</span><span class="sxs-lookup"><span data-stu-id="4eba7-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="4eba7-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="4eba7-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="4eba7-118">Функция не экспортируется из времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="4eba7-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4eba7-119">Требования</span><span class="sxs-lookup"><span data-stu-id="4eba7-119">Requirements</span></span>  
 <span data-ttu-id="4eba7-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4eba7-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4eba7-121">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4eba7-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4eba7-122">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4eba7-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4eba7-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4eba7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eba7-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4eba7-124">See also</span></span>

- [<span data-ttu-id="4eba7-125">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="4eba7-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
