---
title: "Перечисление CorPinvokeMap"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0e0771ce54e7e2973525bfcf4aba4c1f7ddf0a52
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="48392-102">Перечисление CorPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="48392-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="48392-103">Задает параметры для вызова PInvoke.</span><span class="sxs-lookup"><span data-stu-id="48392-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48392-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48392-104">Syntax</span></span>  
  
```  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,   
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a><span data-ttu-id="48392-105">Участники</span><span class="sxs-lookup"><span data-stu-id="48392-105">Members</span></span>  
  
|<span data-ttu-id="48392-106">Член</span><span class="sxs-lookup"><span data-stu-id="48392-106">Member</span></span>|<span data-ttu-id="48392-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="48392-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="48392-108">Используйте имя каждого элемента, как указано.</span><span class="sxs-lookup"><span data-stu-id="48392-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="48392-109">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="48392-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="48392-110">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="48392-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="48392-111">Маршалинг строк как строки многобайтовых символов.</span><span class="sxs-lookup"><span data-stu-id="48392-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="48392-112">Маршалинг строк как 2-байтовые символы Юникода.</span><span class="sxs-lookup"><span data-stu-id="48392-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="48392-113">Выполняет автоматический маршалинг строк, соответствующую целевой операционной системы.</span><span class="sxs-lookup"><span data-stu-id="48392-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="48392-114">Значение по умолчанию — Юникод в Windows NT, Windows 2000, Windows XP и семейства Windows Server 2003; значение по умолчанию — ANSI для Windows 98 и Windows Me.</span><span class="sxs-lookup"><span data-stu-id="48392-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="48392-115">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="48392-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="48392-116">Выполните наилучшего сопоставления символов Юникода, в которых не хватает точного совпадения в наборе символов ANSI.</span><span class="sxs-lookup"><span data-stu-id="48392-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="48392-117">Не выполняйте наилучшего сопоставления символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="48392-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="48392-118">В этом случае всех неотображаемых символов будут заменены "?".</span><span class="sxs-lookup"><span data-stu-id="48392-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="48392-119">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="48392-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="48392-120">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="48392-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="48392-121">Выдает исключение при обнаружении упаковщик взаимодействия несопоставимого символа.</span><span class="sxs-lookup"><span data-stu-id="48392-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="48392-122">Вызывает исключение при обнаружении упаковщик взаимодействия несопоставимого символа.</span><span class="sxs-lookup"><span data-stu-id="48392-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="48392-123">Зарезервированное</span><span class="sxs-lookup"><span data-stu-id="48392-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="48392-124">Разрешить вызываемому вызывать Win32 `SetLastError` функции перед возвратом из метода, использующего атрибуты.</span><span class="sxs-lookup"><span data-stu-id="48392-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="48392-125">Зарезервированное</span><span class="sxs-lookup"><span data-stu-id="48392-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="48392-126">Используйте соглашение о вызовах платформы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="48392-126">Use the default platform calling convention.</span></span> <span data-ttu-id="48392-127">Например, в Windows по умолчанию используется `StdCall` и в Windows CE .NET является `Cdecl`.</span><span class="sxs-lookup"><span data-stu-id="48392-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="48392-128">Используйте `Cdecl` соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="48392-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="48392-129">В этом случае вызывающий объект очищает стек.</span><span class="sxs-lookup"><span data-stu-id="48392-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="48392-130">Это позволяет вызывать функции с `varargs` (функций, принимающих переменное количество параметров).</span><span class="sxs-lookup"><span data-stu-id="48392-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="48392-131">Используйте `StdCall` соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="48392-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="48392-132">В этом случае вызываемый метод очищает стек.</span><span class="sxs-lookup"><span data-stu-id="48392-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="48392-133">Это соглашение по умолчанию для вызова неуправляемых функций с вызовом неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="48392-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="48392-134">Используйте `ThisCall` соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="48392-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="48392-135">В этом случае первый параметр — `this` указателя и хранится в регистре ECX.</span><span class="sxs-lookup"><span data-stu-id="48392-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="48392-136">Другие параметры помещаются в стек.</span><span class="sxs-lookup"><span data-stu-id="48392-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="48392-137">`ThisCall` Соглашение о вызовах используется для вызова методов в классах, экспортированных из неуправляемой библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="48392-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="48392-138">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="48392-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="48392-139">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="48392-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="48392-140">Требования</span><span class="sxs-lookup"><span data-stu-id="48392-140">Requirements</span></span>  
 <span data-ttu-id="48392-141">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48392-141">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48392-142">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="48392-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="48392-143">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48392-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48392-144">См. также</span><span class="sxs-lookup"><span data-stu-id="48392-144">See Also</span></span>  
 [<span data-ttu-id="48392-145">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="48392-145">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
