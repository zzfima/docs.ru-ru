---
title: Функция GetCORVersion
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
ms.openlocfilehash: 1f40f27651d2d75cf2c3e4d7d1c21e1f47d402af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178194"
---
# <a name="getcorversion-function"></a><span data-ttu-id="393d5-102">Функция GetCORVersion</span><span class="sxs-lookup"><span data-stu-id="393d5-102">GetCORVersion Function</span></span>
<span data-ttu-id="393d5-103">Возвращает номер версии общего времени выполнения языка (CLR), который работает в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="393d5-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="393d5-104">Эта функция была унесена в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="393d5-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="393d5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="393d5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="393d5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="393d5-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="393d5-107">Указатель на буфер, в котором CLR возвращает строку с указанием версии времени выполнения, которая в настоящее время загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="393d5-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="393d5-108">Возвращалась строка принимает ту же форму, что и строки, передаваемые [CorBindToRuntimeEx,](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)например, "v1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="393d5-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="393d5-109">Если время выполнения еще не загружено в процесс, функция возвращает соответствующую информацию каталога для последней версии времени выполнения, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="393d5-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="393d5-110">Количество символов (ы),`WCHAR`которые могут `pbuffer`быть проведены в .</span><span class="sxs-lookup"><span data-stu-id="393d5-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="393d5-111">Указатель на количество символов на `pbuffer`самом деле вернулся в .</span><span class="sxs-lookup"><span data-stu-id="393d5-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="393d5-112">Если `pbuffer` это нулевая указка, время выполнения возвращается E_POINTER.</span><span class="sxs-lookup"><span data-stu-id="393d5-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="393d5-113">Если количество символов больше, то `pbuffer` длина, время выполнения возвращается ERROR_INSUFFICIENT_BUFFER.</span><span class="sxs-lookup"><span data-stu-id="393d5-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="393d5-114">Требования</span><span class="sxs-lookup"><span data-stu-id="393d5-114">Requirements</span></span>  
 <span data-ttu-id="393d5-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="393d5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="393d5-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="393d5-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="393d5-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="393d5-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="393d5-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="393d5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="393d5-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="393d5-119">See also</span></span>

- [<span data-ttu-id="393d5-120">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="393d5-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
