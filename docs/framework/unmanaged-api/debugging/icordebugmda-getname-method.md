---
title: Метод ICorDebugMDA::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type:
- apiref
ms.openlocfilehash: 1b19ce5e9f795fd9ff4dd15e10256a150063a314
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128046"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="0c7b3-102">Метод ICorDebugMDA::GetName</span><span class="sxs-lookup"><span data-stu-id="0c7b3-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="0c7b3-103">Возвращает строку, содержащую имя помощника по отладке управляемого кода (MDA), представленного [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="0c7b3-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c7b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c7b3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c7b3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0c7b3-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="0c7b3-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="0c7b3-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0c7b3-107">заполняет Указатель на длину имени.</span><span class="sxs-lookup"><span data-stu-id="0c7b3-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="0c7b3-108">заполняет Массив, в котором сохраняется имя.</span><span class="sxs-lookup"><span data-stu-id="0c7b3-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c7b3-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="0c7b3-109">Remarks</span></span>  
 <span data-ttu-id="0c7b3-110">Имена MDA являются уникальными значениями.</span><span class="sxs-lookup"><span data-stu-id="0c7b3-110">MDA names are unique values.</span></span> <span data-ttu-id="0c7b3-111">Метод `GetName` является удобной альтернативой производительности для получения XML-потока и извлечения имени из потока на основе схемы.</span><span class="sxs-lookup"><span data-stu-id="0c7b3-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c7b3-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0c7b3-112">Requirements</span></span>  
 <span data-ttu-id="0c7b3-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c7b3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c7b3-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c7b3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c7b3-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c7b3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c7b3-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c7b3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c7b3-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0c7b3-117">See also</span></span>

- [<span data-ttu-id="0c7b3-118">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="0c7b3-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="0c7b3-119">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="0c7b3-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
