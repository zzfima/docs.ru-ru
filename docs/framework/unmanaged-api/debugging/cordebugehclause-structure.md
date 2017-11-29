---
title: "Структура CorDebugEHClause"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: CorDebugEHClause
api_location: mscordbi.dll
api_type: COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 154bbe14a14d34c0d998e3192a70a96b9922f32c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugehclause-structure"></a><span data-ttu-id="52f11-102">Структура CorDebugEHClause</span><span class="sxs-lookup"><span data-stu-id="52f11-102">CorDebugEHClause Structure</span></span>
<span data-ttu-id="52f11-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="52f11-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="52f11-104">Представляет предложение обработки исключений для данного фрагмента кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="52f11-104">Represents an exception handling (EH) clause for a given piece of intermediate language (IL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52f11-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52f11-105">Syntax</span></span>  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a><span data-ttu-id="52f11-106">Члены</span><span class="sxs-lookup"><span data-stu-id="52f11-106">Members</span></span>  
  
|<span data-ttu-id="52f11-107">Член</span><span class="sxs-lookup"><span data-stu-id="52f11-107">Member</span></span>|<span data-ttu-id="52f11-108">Описание</span><span class="sxs-lookup"><span data-stu-id="52f11-108">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="52f11-109">Битовое поле, описывающее информацию об исключениях в предложении обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="52f11-109">A bit field that describes the exception information in the EH clause.</span></span> <span data-ttu-id="52f11-110">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="52f11-110">For more information, see the Remarks section.</span></span>|  
|`TryOffset`|<span data-ttu-id="52f11-111">Смещение блока `try` в байтах от начала тела метода.</span><span class="sxs-lookup"><span data-stu-id="52f11-111">The offset, in bytes, of the `try` block from the start of the method body.</span></span>|  
|`TryLength`|<span data-ttu-id="52f11-112">Длина блока `try` в байтах.</span><span class="sxs-lookup"><span data-stu-id="52f11-112">The length, in bytes, of the `try` block.</span></span>|  
|`HandlerOffset`|<span data-ttu-id="52f11-113">Расположение обработчика для этого блока `try`.</span><span class="sxs-lookup"><span data-stu-id="52f11-113">The location of the handler for this `try` block.</span></span>|  
|`HandlerLength`|<span data-ttu-id="52f11-114">Размер кода обработчика в байтах.</span><span class="sxs-lookup"><span data-stu-id="52f11-114">The size of the handler code in bytes.</span></span>|  
|`ClassToken`|<span data-ttu-id="52f11-115">Токен метаданных для обработчика исключений на основе типа.</span><span class="sxs-lookup"><span data-stu-id="52f11-115">The metadata token for a type-based exception handler.</span></span>|  
|`FilterOffset`|<span data-ttu-id="52f11-116">Смещение в байтах от начала тела метода для обработчика исключений на основе фильтра.</span><span class="sxs-lookup"><span data-stu-id="52f11-116">The offset, in bytes, from the start of the method body for a filter-based exception handler.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52f11-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="52f11-117">Remarks</span></span>  
 <span data-ttu-id="52f11-118">Массив `CoreDebugEHClause` возвращенных значений [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="52f11-118">An array of `CoreDebugEHClause` values is returned by the [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) method.</span></span>  
  
 <span data-ttu-id="52f11-119">Информация о предложении обработки исключений определяется спецификацией CLI.</span><span class="sxs-lookup"><span data-stu-id="52f11-119">The EH clause information is defined by the CLI specification.</span></span> <span data-ttu-id="52f11-120">Дополнительные сведения см. в разделе [стандартные ECMA-355: Common Language Infrastructure (CLI), изд](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="52f11-120">For more information, see [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
 <span data-ttu-id="52f11-121">Поле `flags` может содержать следующие флаги.</span><span class="sxs-lookup"><span data-stu-id="52f11-121">The `flags` field can contain the following flags.</span></span> <span data-ttu-id="52f11-122">Обратите внимание, что они не определены в CorDebug.idl или CorDebug.h.</span><span class="sxs-lookup"><span data-stu-id="52f11-122">Note that they are not defined in CorDebug.idl or CorDebug.h.</span></span>  
  
|<span data-ttu-id="52f11-123">Flag</span><span class="sxs-lookup"><span data-stu-id="52f11-123">Flag</span></span>|<span data-ttu-id="52f11-124">Значение</span><span class="sxs-lookup"><span data-stu-id="52f11-124">Value</span></span>|<span data-ttu-id="52f11-125">Описание</span><span class="sxs-lookup"><span data-stu-id="52f11-125">Description</span></span>|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|<span data-ttu-id="52f11-126">0x00000000</span><span class="sxs-lookup"><span data-stu-id="52f11-126">0x00000000</span></span>|<span data-ttu-id="52f11-127">Введенное предложение исключений.</span><span class="sxs-lookup"><span data-stu-id="52f11-127">A typed exception clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|<span data-ttu-id="52f11-128">0x00000001</span><span class="sxs-lookup"><span data-stu-id="52f11-128">0x00000001</span></span>|<span data-ttu-id="52f11-129">Фильтр исключений и предложение обработчика.</span><span class="sxs-lookup"><span data-stu-id="52f11-129">An exception filter and handler clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|<span data-ttu-id="52f11-130">0x00000002</span><span class="sxs-lookup"><span data-stu-id="52f11-130">0x00000002</span></span>|<span data-ttu-id="52f11-131">Предложение `finally`.</span><span class="sxs-lookup"><span data-stu-id="52f11-131">A `finally` clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|<span data-ttu-id="52f11-132">0x00000004</span><span class="sxs-lookup"><span data-stu-id="52f11-132">0x00000004</span></span>|<span data-ttu-id="52f11-133">Неправильное предложение (предложение `finally`, которое вызывается только при возникновении исключения).</span><span class="sxs-lookup"><span data-stu-id="52f11-133">A fault clause (a `finally` clause that is called only when an exception is thrown).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52f11-134">Требования</span><span class="sxs-lookup"><span data-stu-id="52f11-134">Requirements</span></span>  
 <span data-ttu-id="52f11-135">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52f11-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52f11-136">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52f11-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52f11-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52f11-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52f11-138">**Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52f11-138">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52f11-139">См. также</span><span class="sxs-lookup"><span data-stu-id="52f11-139">See Also</span></span>  
 [<span data-ttu-id="52f11-140">Метод GetEHClauses</span><span class="sxs-lookup"><span data-stu-id="52f11-140">GetEHClauses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)  
 [<span data-ttu-id="52f11-141">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="52f11-141">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
