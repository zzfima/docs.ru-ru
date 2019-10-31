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
ms.openlocfilehash: 5e3619d12b9377a8482254703d3d97d0348a013b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127175"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="c9f8a-102">Метод ICorDebugAssembly::GetName</span><span class="sxs-lookup"><span data-stu-id="c9f8a-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="c9f8a-103">Возвращает имя сборки, которую представляет данный экземпляр `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="c9f8a-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9f8a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9f8a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9f8a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c9f8a-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="c9f8a-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="c9f8a-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c9f8a-107">заполняет Указатель на целое число, задающее фактическую длину имени.</span><span class="sxs-lookup"><span data-stu-id="c9f8a-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="c9f8a-108">заполняет Массив, в котором хранится имя.</span><span class="sxs-lookup"><span data-stu-id="c9f8a-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9f8a-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="c9f8a-109">Remarks</span></span>  
 <span data-ttu-id="c9f8a-110">Метод `GetName` возвращает полный путь и имя файла сборки.</span><span class="sxs-lookup"><span data-stu-id="c9f8a-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9f8a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c9f8a-111">Requirements</span></span>  
 <span data-ttu-id="c9f8a-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9f8a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9f8a-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9f8a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9f8a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9f8a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9f8a-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9f8a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
