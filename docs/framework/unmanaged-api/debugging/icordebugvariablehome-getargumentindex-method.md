---
title: Метод ICorDebugVariableHome::GetArgumentIndex
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2457dff3063e47f1fb9d040caac1bc08441e1739
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366833"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="e99bd-102">Метод ICorDebugVariableHome::GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="e99bd-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="e99bd-103">Получает индекс аргумента функции.</span><span class="sxs-lookup"><span data-stu-id="e99bd-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="e99bd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e99bd-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="e99bd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e99bd-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="e99bd-106">[out] Указатель на индекс аргумента.</span><span class="sxs-lookup"><span data-stu-id="e99bd-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="e99bd-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e99bd-107">Return Value</span></span>

<span data-ttu-id="e99bd-108">Метод возвращает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="e99bd-108">The method returns the following values.</span></span>

|<span data-ttu-id="e99bd-109">Значение</span><span class="sxs-lookup"><span data-stu-id="e99bd-109">Value</span></span>|<span data-ttu-id="e99bd-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="e99bd-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="e99bd-111">Вызов метода вернул индекс допустимый аргумент.</span><span class="sxs-lookup"><span data-stu-id="e99bd-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="e99bd-112">Текущий [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) экземпляр представляет локальную переменную.</span><span class="sxs-lookup"><span data-stu-id="e99bd-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e99bd-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="e99bd-113">Remarks</span></span>

<span data-ttu-id="e99bd-114">Аргумент индекса можно использовать для получения метаданных для этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="e99bd-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="e99bd-115">Требования</span><span class="sxs-lookup"><span data-stu-id="e99bd-115">Requirements</span></span>

<span data-ttu-id="e99bd-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e99bd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="e99bd-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e99bd-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="e99bd-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e99bd-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="e99bd-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e99bd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e99bd-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e99bd-120">See also</span></span>

- [<span data-ttu-id="e99bd-121">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="e99bd-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
