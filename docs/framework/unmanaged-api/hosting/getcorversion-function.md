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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f66e00c3334aecdf8c653f57e28d1b327c4170e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628006"
---
# <a name="getcorversion-function"></a><span data-ttu-id="717ca-102">Функция GetCORVersion</span><span class="sxs-lookup"><span data-stu-id="717ca-102">GetCORVersion Function</span></span>
<span data-ttu-id="717ca-103">Возвращает номер версии среда CLR (CLR), на котором выполняется в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="717ca-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="717ca-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="717ca-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="717ca-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="717ca-105">Syntax</span></span>  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="717ca-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="717ca-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="717ca-107">Указатель на буфер, в котором среда CLR возвращает строку, представляющую версию среды выполнения, который в данный момент загружается процесс.</span><span class="sxs-lookup"><span data-stu-id="717ca-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="717ca-108">Возвращаемая строка принимает ту же форму, как строки, переданной в [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), например, «v1.0.1216».</span><span class="sxs-lookup"><span data-stu-id="717ca-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="717ca-109">Если среда выполнения еще не был загружен в процесс, функция возвращает данные каталога, соответствующего для последней версии среды выполнения, установленную на компьютере.</span><span class="sxs-lookup"><span data-stu-id="717ca-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="717ca-110">Число символов (`WCHAR`s), могут храниться в `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="717ca-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="717ca-111">Указатель на число символов, фактически возвращенных в `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="717ca-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="717ca-112">Если `pbuffer` является пустым указателем, среда выполнения возвращает E_POINTER.</span><span class="sxs-lookup"><span data-stu-id="717ca-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="717ca-113">Если количество символов больше длины `pbuffer` , среда выполнения возвращает значение ERROR_INSUFFICIENT_BUFFER.</span><span class="sxs-lookup"><span data-stu-id="717ca-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="717ca-114">Требования</span><span class="sxs-lookup"><span data-stu-id="717ca-114">Requirements</span></span>  
 <span data-ttu-id="717ca-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="717ca-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="717ca-116">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="717ca-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="717ca-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="717ca-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="717ca-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="717ca-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="717ca-119">См. также</span><span class="sxs-lookup"><span data-stu-id="717ca-119">See also</span></span>

- [<span data-ttu-id="717ca-120">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="717ca-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
