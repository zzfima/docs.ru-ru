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
ms.openlocfilehash: 12d4e63480f03bfad613f30362ddaeaf12b57a88
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791053"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="39209-102">Метод ICorDebugVariableHome:: Жетаргументиндекс</span><span class="sxs-lookup"><span data-stu-id="39209-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="39209-103">Возвращает индекс аргумента функции.</span><span class="sxs-lookup"><span data-stu-id="39209-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="39209-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39209-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="39209-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="39209-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="39209-106">заполняет Указатель на индекс аргумента.</span><span class="sxs-lookup"><span data-stu-id="39209-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="39209-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="39209-107">Return Value</span></span>

<span data-ttu-id="39209-108">Метод возвращает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="39209-108">The method returns the following values.</span></span>

|<span data-ttu-id="39209-109">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="39209-109">Value</span></span>|<span data-ttu-id="39209-110">Описание</span><span class="sxs-lookup"><span data-stu-id="39209-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="39209-111">Вызов метода вернул допустимый индекс аргумента.</span><span class="sxs-lookup"><span data-stu-id="39209-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="39209-112">Текущий экземпляр [ICorDebugVariableHome](icordebugvariablehome-interface.md) представляет локальную переменную.</span><span class="sxs-lookup"><span data-stu-id="39209-112">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="39209-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="39209-113">Remarks</span></span>

<span data-ttu-id="39209-114">Индекс аргумента можно использовать для получения метаданных для этого аргумента.</span><span class="sxs-lookup"><span data-stu-id="39209-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="39209-115">Требования</span><span class="sxs-lookup"><span data-stu-id="39209-115">Requirements</span></span>

<span data-ttu-id="39209-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39209-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="39209-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39209-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="39209-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39209-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="39209-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39209-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="39209-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="39209-120">See also</span></span>

- [<span data-ttu-id="39209-121">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="39209-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
