---
title: Метод ICorDebugModule2::ResolveAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
ms.openlocfilehash: 0809a149a5a5a5e9adea059140d7b4b456337ef3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125303"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="5006d-102">Метод ICorDebugModule2::ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="5006d-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="5006d-103">Разрешает сборку, на которую ссылается указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="5006d-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="5006d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5006d-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="5006d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5006d-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="5006d-106">окне Значение `mdToken`, которое ссылается на сборку.</span><span class="sxs-lookup"><span data-stu-id="5006d-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="5006d-107">заполняет Указатель на адрес объекта ICorDebugAssembly, который представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="5006d-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="5006d-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="5006d-108">Remarks</span></span>

<span data-ttu-id="5006d-109">Если сборка еще не загружена при вызове `ResolveAssembly`, возвращается значение HRESULT CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="5006d-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="5006d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5006d-110">Requirements</span></span>

<span data-ttu-id="5006d-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5006d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="5006d-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5006d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="5006d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5006d-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5006d-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5006d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
