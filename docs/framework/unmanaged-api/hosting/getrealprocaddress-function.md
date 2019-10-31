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
ms.openlocfilehash: 9dffc3d197b05bb71443aa60c101260daabadadd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136392"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="53057-102">Функция GetRealProcAddress</span><span class="sxs-lookup"><span data-stu-id="53057-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="53057-103">Возвращает адрес указанной функции, которая экспортируется из последней установленной версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="53057-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="53057-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="53057-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53057-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53057-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53057-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="53057-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="53057-107">окне Имя функции.</span><span class="sxs-lookup"><span data-stu-id="53057-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="53057-108">заполняет Расположение, которое получает указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="53057-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53057-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="53057-109">Return Value</span></span>  
 <span data-ttu-id="53057-110">Этот метод возвращает коды стандартных ошибок модели COM, как определено в файле WinError. h, в дополнение к следующим значениям, определенным в CorError. h.</span><span class="sxs-lookup"><span data-stu-id="53057-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="53057-111">Код возврата</span><span class="sxs-lookup"><span data-stu-id="53057-111">Return code</span></span>|<span data-ttu-id="53057-112">Описание</span><span class="sxs-lookup"><span data-stu-id="53057-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="53057-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="53057-113">S_OK</span></span>|<span data-ttu-id="53057-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="53057-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="53057-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="53057-115">E_POINTER</span></span>|<span data-ttu-id="53057-116">Недопустимый параметр `ppv`.</span><span class="sxs-lookup"><span data-stu-id="53057-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="53057-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="53057-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="53057-118">Функция не экспортируется из среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="53057-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53057-119">Требования</span><span class="sxs-lookup"><span data-stu-id="53057-119">Requirements</span></span>  
 <span data-ttu-id="53057-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53057-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53057-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="53057-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53057-122">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="53057-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53057-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53057-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53057-124">См. также</span><span class="sxs-lookup"><span data-stu-id="53057-124">See also</span></span>

- [<span data-ttu-id="53057-125">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="53057-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
