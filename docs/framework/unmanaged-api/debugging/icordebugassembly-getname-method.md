---
title: Метод ICorDebugAssembly::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3077e0494816a083d97839d66d06b18130e5dac8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645582"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="582d4-102">Метод ICorDebugAssembly::GetName</span><span class="sxs-lookup"><span data-stu-id="582d4-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="582d4-103">Возвращает имя сборки, это `ICorDebugAssembly` представленное экземпляром.</span><span class="sxs-lookup"><span data-stu-id="582d4-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="582d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="582d4-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="582d4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="582d4-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="582d4-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="582d4-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="582d4-107">[out] Указатель на целое число, которое указывает фактическую длину имени.</span><span class="sxs-lookup"><span data-stu-id="582d4-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="582d4-108">[out] Массив, в котором хранится имя.</span><span class="sxs-lookup"><span data-stu-id="582d4-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="582d4-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="582d4-109">Remarks</span></span>  
 <span data-ttu-id="582d4-110">`GetName` Метод возвращает полный путь и имя сборки.</span><span class="sxs-lookup"><span data-stu-id="582d4-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="582d4-111">Требования</span><span class="sxs-lookup"><span data-stu-id="582d4-111">Requirements</span></span>  
 <span data-ttu-id="582d4-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="582d4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="582d4-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="582d4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="582d4-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="582d4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="582d4-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="582d4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
