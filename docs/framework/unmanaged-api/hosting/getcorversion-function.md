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
ms.openlocfilehash: 1283abaf6b08af1d842d8fe4469f7f6c15e38ec5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136425"
---
# <a name="getcorversion-function"></a><span data-ttu-id="b9717-102">Функция GetCORVersion</span><span class="sxs-lookup"><span data-stu-id="b9717-102">GetCORVersion Function</span></span>
<span data-ttu-id="b9717-103">Возвращает номер версии общеязыковой среды выполнения (CLR), которая выполняется в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="b9717-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="b9717-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b9717-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9717-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9717-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="b9717-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9717-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="b9717-107">Указатель на буфер, в котором среда CLR возвращает строку, указывающую версию среды выполнения, которая в данный момент загружена в процесс.</span><span class="sxs-lookup"><span data-stu-id="b9717-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="b9717-108">Возвращаемая строка принимает ту же форму, что и строки, переданные в [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), например "v 1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="b9717-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="b9717-109">Если среда выполнения еще не загружена в процесс, функция возвращает соответствующие сведения о каталоге для последней версии среды выполнения, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b9717-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="b9717-110">Число символов (`WCHAR`s), которые могут храниться в `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="b9717-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="b9717-111">Указатель на число символов, фактически возвращаемых в `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="b9717-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="b9717-112">Если `pbuffer` является пустым указателем, среда выполнения возвращает E_POINTER.</span><span class="sxs-lookup"><span data-stu-id="b9717-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="b9717-113">Если число символов превышает длину `pbuffer`, среда выполнения возвращает ERROR_INSUFFICIENT_BUFFER.</span><span class="sxs-lookup"><span data-stu-id="b9717-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9717-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b9717-114">Requirements</span></span>  
 <span data-ttu-id="b9717-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9717-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9717-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b9717-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9717-117">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b9717-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9717-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9717-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9717-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b9717-119">See also</span></span>

- [<span data-ttu-id="b9717-120">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="b9717-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
