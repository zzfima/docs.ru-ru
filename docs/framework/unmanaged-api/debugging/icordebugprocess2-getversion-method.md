---
title: Метод ICorDebugProcess2::GetVersion
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 interface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07f3be81431201a4bb6011ea9b8f973061d3d101
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948878"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="720b9-102">Метод ICorDebugProcess2::GetVersion</span><span class="sxs-lookup"><span data-stu-id="720b9-102">ICorDebugProcess2::GetVersion Method</span></span>

<span data-ttu-id="720b9-103">Возвращает номер версии среда CLR (CLR), на котором выполняется в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="720b9-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>

## <a name="syntax"></a><span data-ttu-id="720b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="720b9-104">Syntax</span></span>

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a><span data-ttu-id="720b9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="720b9-105">Parameters</span></span>

`version`\
<span data-ttu-id="720b9-106">[out] Указатель на структуру COR_VERSION, которая хранит номер версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="720b9-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>

## <a name="remarks"></a><span data-ttu-id="720b9-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="720b9-107">Remarks</span></span>

<span data-ttu-id="720b9-108">`GetVersion` Метод возвращает код ошибки, если среда выполнения не была загружена в процесс.</span><span class="sxs-lookup"><span data-stu-id="720b9-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>

## <a name="requirements"></a><span data-ttu-id="720b9-109">Требования</span><span class="sxs-lookup"><span data-stu-id="720b9-109">Requirements</span></span>

<span data-ttu-id="720b9-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="720b9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="720b9-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="720b9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="720b9-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="720b9-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="720b9-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="720b9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
