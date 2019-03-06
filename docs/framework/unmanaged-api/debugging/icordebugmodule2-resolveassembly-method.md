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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd899422287d34407778f67e5b4dfd2f33ffd00c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359696"
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="d12f5-102">Метод ICorDebugModule2::ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="d12f5-102">ICorDebugModule2::ResolveAssembly Method</span></span>

<span data-ttu-id="d12f5-103">Разрешает сборки, упоминаемой в заданным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="d12f5-103">Resolves the assembly referenced by the specified metadata token.</span></span>

## <a name="syntax"></a><span data-ttu-id="d12f5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d12f5-104">Syntax</span></span>

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a><span data-ttu-id="d12f5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d12f5-105">Parameters</span></span>

`tkAssemblyRef`\
<span data-ttu-id="d12f5-106">[in] `mdToken` Значение, которое ссылается на сборку.</span><span class="sxs-lookup"><span data-stu-id="d12f5-106">[in] An `mdToken` value that references the assembly.</span></span>

`ppAssembly`\
<span data-ttu-id="d12f5-107">[out] Указатель на адрес объекта ICorDebugAssembly, представляющий сборку.</span><span class="sxs-lookup"><span data-stu-id="d12f5-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="d12f5-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="d12f5-108">Remarks</span></span>

<span data-ttu-id="d12f5-109">Если сборка еще не загружен при `ResolveAssembly` вызывается HRESULT возвращается значение CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="d12f5-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="d12f5-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d12f5-110">Requirements</span></span>

<span data-ttu-id="d12f5-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d12f5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d12f5-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d12f5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="d12f5-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d12f5-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d12f5-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d12f5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
