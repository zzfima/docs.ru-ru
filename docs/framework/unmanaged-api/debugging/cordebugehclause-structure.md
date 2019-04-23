---
title: Структура CorDebugEHClause
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 839e698c8921f916fad174bae4f4cc8bb4d02994
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157330"
---
# <a name="cordebugehclause-structure"></a><span data-ttu-id="ebc60-102">Структура CorDebugEHClause</span><span class="sxs-lookup"><span data-stu-id="ebc60-102">CorDebugEHClause Structure</span></span>
<span data-ttu-id="ebc60-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="ebc60-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ebc60-104">Представляет предложение обработки исключений для данного фрагмента кода промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="ebc60-104">Represents an exception handling (EH) clause for a given piece of intermediate language (IL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebc60-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebc60-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ebc60-106">Участники</span><span class="sxs-lookup"><span data-stu-id="ebc60-106">Members</span></span>  
  
|<span data-ttu-id="ebc60-107">Член</span><span class="sxs-lookup"><span data-stu-id="ebc60-107">Member</span></span>|<span data-ttu-id="ebc60-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ebc60-108">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="ebc60-109">Битовое поле, описывающее информацию об исключениях в предложении обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="ebc60-109">A bit field that describes the exception information in the EH clause.</span></span> <span data-ttu-id="ebc60-110">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="ebc60-110">For more information, see the Remarks section.</span></span>|  
|`TryOffset`|<span data-ttu-id="ebc60-111">Смещение блока `try` в байтах от начала тела метода.</span><span class="sxs-lookup"><span data-stu-id="ebc60-111">The offset, in bytes, of the `try` block from the start of the method body.</span></span>|  
|`TryLength`|<span data-ttu-id="ebc60-112">Длина блока `try` в байтах.</span><span class="sxs-lookup"><span data-stu-id="ebc60-112">The length, in bytes, of the `try` block.</span></span>|  
|`HandlerOffset`|<span data-ttu-id="ebc60-113">Расположение обработчика для этого блока `try`.</span><span class="sxs-lookup"><span data-stu-id="ebc60-113">The location of the handler for this `try` block.</span></span>|  
|`HandlerLength`|<span data-ttu-id="ebc60-114">Размер кода обработчика в байтах.</span><span class="sxs-lookup"><span data-stu-id="ebc60-114">The size of the handler code in bytes.</span></span>|  
|`ClassToken`|<span data-ttu-id="ebc60-115">Токен метаданных для обработчика исключений на основе типа.</span><span class="sxs-lookup"><span data-stu-id="ebc60-115">The metadata token for a type-based exception handler.</span></span>|  
|`FilterOffset`|<span data-ttu-id="ebc60-116">Смещение в байтах от начала тела метода для обработчика исключений на основе фильтра.</span><span class="sxs-lookup"><span data-stu-id="ebc60-116">The offset, in bytes, from the start of the method body for a filter-based exception handler.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebc60-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="ebc60-117">Remarks</span></span>  
 <span data-ttu-id="ebc60-118">Массив `CoreDebugEHClause` возвращаемые значения [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="ebc60-118">An array of `CoreDebugEHClause` values is returned by the [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) method.</span></span>  
  
 <span data-ttu-id="ebc60-119">Информация о предложении обработки исключений определяется спецификацией CLI.</span><span class="sxs-lookup"><span data-stu-id="ebc60-119">The EH clause information is defined by the CLI specification.</span></span> <span data-ttu-id="ebc60-120">Дополнительные сведения см. в разделе [стандартный ECMA-355: Common Language Infrastructure (CLI), изд. 6](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="ebc60-120">For more information, see [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
 <span data-ttu-id="ebc60-121">Поле `flags` может содержать следующие флаги.</span><span class="sxs-lookup"><span data-stu-id="ebc60-121">The `flags` field can contain the following flags.</span></span> <span data-ttu-id="ebc60-122">Обратите внимание, что они не определены в CorDebug.idl или CorDebug.h.</span><span class="sxs-lookup"><span data-stu-id="ebc60-122">Note that they are not defined in CorDebug.idl or CorDebug.h.</span></span>  
  
|<span data-ttu-id="ebc60-123">Flag</span><span class="sxs-lookup"><span data-stu-id="ebc60-123">Flag</span></span>|<span data-ttu-id="ebc60-124">Значение</span><span class="sxs-lookup"><span data-stu-id="ebc60-124">Value</span></span>|<span data-ttu-id="ebc60-125">Описание</span><span class="sxs-lookup"><span data-stu-id="ebc60-125">Description</span></span>|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|<span data-ttu-id="ebc60-126">0x00000000</span><span class="sxs-lookup"><span data-stu-id="ebc60-126">0x00000000</span></span>|<span data-ttu-id="ebc60-127">Введенное предложение исключений.</span><span class="sxs-lookup"><span data-stu-id="ebc60-127">A typed exception clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|<span data-ttu-id="ebc60-128">0x00000001</span><span class="sxs-lookup"><span data-stu-id="ebc60-128">0x00000001</span></span>|<span data-ttu-id="ebc60-129">Фильтр исключений и предложение обработчика.</span><span class="sxs-lookup"><span data-stu-id="ebc60-129">An exception filter and handler clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|<span data-ttu-id="ebc60-130">0x00000002</span><span class="sxs-lookup"><span data-stu-id="ebc60-130">0x00000002</span></span>|<span data-ttu-id="ebc60-131">Предложение `finally`.</span><span class="sxs-lookup"><span data-stu-id="ebc60-131">A `finally` clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|<span data-ttu-id="ebc60-132">0x00000004</span><span class="sxs-lookup"><span data-stu-id="ebc60-132">0x00000004</span></span>|<span data-ttu-id="ebc60-133">Неправильное предложение (предложение `finally`, которое вызывается только при возникновении исключения).</span><span class="sxs-lookup"><span data-stu-id="ebc60-133">A fault clause (a `finally` clause that is called only when an exception is thrown).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ebc60-134">Требования</span><span class="sxs-lookup"><span data-stu-id="ebc60-134">Requirements</span></span>  
 <span data-ttu-id="ebc60-135">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebc60-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebc60-136">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ebc60-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ebc60-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebc60-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebc60-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebc60-138">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc60-139">См. также</span><span class="sxs-lookup"><span data-stu-id="ebc60-139">See also</span></span>

- [<span data-ttu-id="ebc60-140">Метод GetEHClauses</span><span class="sxs-lookup"><span data-stu-id="ebc60-140">GetEHClauses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)
- [<span data-ttu-id="ebc60-141">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="ebc60-141">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
