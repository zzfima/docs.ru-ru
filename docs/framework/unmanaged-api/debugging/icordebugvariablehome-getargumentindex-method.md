---
title: 'Метод ICorDebugVariableHome:: Жетаргументиндекс'
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
ms.openlocfilehash: 86b2815c6f95c674c49bba7455e8497192bd8bac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125151"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="b45e5-102">Метод ICorDebugVariableHome:: Жетаргументиндекс</span><span class="sxs-lookup"><span data-stu-id="b45e5-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="b45e5-103">Возвращает индекс аргумента функции.</span><span class="sxs-lookup"><span data-stu-id="b45e5-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="b45e5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b45e5-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="b45e5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b45e5-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="b45e5-106">заполняет Указатель на индекс аргумента.</span><span class="sxs-lookup"><span data-stu-id="b45e5-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="b45e5-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b45e5-107">Return Value</span></span>

<span data-ttu-id="b45e5-108">Метод возвращает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="b45e5-108">The method returns the following values.</span></span>

|<span data-ttu-id="b45e5-109">значения</span><span class="sxs-lookup"><span data-stu-id="b45e5-109">Value</span></span>|<span data-ttu-id="b45e5-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b45e5-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="b45e5-111">Вызов метода вернул допустимый индекс аргумента.</span><span class="sxs-lookup"><span data-stu-id="b45e5-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="b45e5-112">Текущий экземпляр [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) представляет локальную переменную.</span><span class="sxs-lookup"><span data-stu-id="b45e5-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b45e5-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="b45e5-113">Remarks</span></span>

<span data-ttu-id="b45e5-114">Индекс аргумента можно использовать для получения метаданных для этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="b45e5-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="b45e5-115">Требования</span><span class="sxs-lookup"><span data-stu-id="b45e5-115">Requirements</span></span>

<span data-ttu-id="b45e5-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b45e5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="b45e5-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b45e5-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="b45e5-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b45e5-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="b45e5-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b45e5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b45e5-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b45e5-120">See also</span></span>

- [<span data-ttu-id="b45e5-121">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="b45e5-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
