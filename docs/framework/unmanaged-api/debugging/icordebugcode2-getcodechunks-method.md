---
title: Метод ICorDebugCode2::GetCodeChunks
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d64773aa0d35f2e97232576d145dfcba624812ec
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395528"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="18e5b-102">Метод ICorDebugCode2::GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="18e5b-102">ICorDebugCode2::GetCodeChunks Method</span></span>

<span data-ttu-id="18e5b-103">Возвращает фрагменты кода, из которого состоит этот объект кода.</span><span class="sxs-lookup"><span data-stu-id="18e5b-103">Gets the chunks of code that this code object is composed of.</span></span>

## <a name="syntax"></a><span data-ttu-id="18e5b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18e5b-104">Syntax</span></span>

```cpp
HRESULT GetCodeChunks (
    [in]  ULONG32     cbufSize,
    [out] ULONG32     *pcnumChunks,
    [out, size_is(cbufSize), length_is(*pcnumChunks)]
        CodeChunkInfo chunks[]
);
```

## <a name="parameters"></a><span data-ttu-id="18e5b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="18e5b-105">Parameters</span></span>

`cbufSize`  
<span data-ttu-id="18e5b-106">окне Размер массива `chunks`.</span><span class="sxs-lookup"><span data-stu-id="18e5b-106">[in] Size of the `chunks` array.</span></span>

`pcnumChunks`  
<span data-ttu-id="18e5b-107">заполняет Число блоков, возвращаемых в массиве `chunks`.</span><span class="sxs-lookup"><span data-stu-id="18e5b-107">[out] The number of chunks returned in the `chunks` array.</span></span>

`chunks`  
<span data-ttu-id="18e5b-108">заполняет Массив структур "Кодечункинфо", каждый из которых представляет отдельный фрагмент кода.</span><span class="sxs-lookup"><span data-stu-id="18e5b-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="18e5b-109">Если значение `cbufSize` равно 0, то этот параметр может иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="18e5b-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>

## <a name="remarks"></a><span data-ttu-id="18e5b-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="18e5b-110">Remarks</span></span>

<span data-ttu-id="18e5b-111">Фрагменты кода никогда не перекрываются, и они будут следовать порядку, в котором они были сцеплены с помощью [ICorDebugCode:: Code](icordebugcode-getcode-method.md).</span><span class="sxs-lookup"><span data-stu-id="18e5b-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="18e5b-112">Объект кода на языке MSIL в .NET Framework версии 2,0 будет состоять из одного фрагмента кода.</span><span class="sxs-lookup"><span data-stu-id="18e5b-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>

## <a name="requirements"></a><span data-ttu-id="18e5b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="18e5b-113">Requirements</span></span>

<span data-ttu-id="18e5b-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18e5b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="18e5b-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18e5b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="18e5b-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18e5b-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="18e5b-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18e5b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
