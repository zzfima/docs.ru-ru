---
title: Метод ICorDebugMDA::GetDescription
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetDescription
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetDescription
helpviewer_keywords:
- GetDescription method [.NET Framework debugging]
- ICorDebugMDA::GetDescription method [.NET Framework debugging]
ms.assetid: 01d1b481-ca67-4712-8744-d342ec0df639
topic_type:
- apiref
ms.openlocfilehash: bfe77982b88b2fc96dc2846b9db04df28bfc0c38
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131447"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="cc4fd-102">Метод ICorDebugMDA::GetDescription</span><span class="sxs-lookup"><span data-stu-id="cc4fd-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="cc4fd-103">Возвращает строку, содержащую описание помощника по отладке управляемого кода (MDA), представленного [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="cc4fd-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc4fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc4fd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc4fd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc4fd-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="cc4fd-106">окне Размер строкового буфера, в котором будет храниться описание.</span><span class="sxs-lookup"><span data-stu-id="cc4fd-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="cc4fd-107">заполняет Указатель на число байтов, возвращенных в буфере строк.</span><span class="sxs-lookup"><span data-stu-id="cc4fd-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="cc4fd-108">заполняет Строковый буфер, содержащий описание MDA.</span><span class="sxs-lookup"><span data-stu-id="cc4fd-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc4fd-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="cc4fd-109">Remarks</span></span>  
 <span data-ttu-id="cc4fd-110">Строка может иметь нулевую длину.</span><span class="sxs-lookup"><span data-stu-id="cc4fd-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc4fd-111">Требования</span><span class="sxs-lookup"><span data-stu-id="cc4fd-111">Requirements</span></span>  
 <span data-ttu-id="cc4fd-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc4fd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc4fd-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc4fd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc4fd-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc4fd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc4fd-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc4fd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc4fd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="cc4fd-116">See also</span></span>

- [<span data-ttu-id="cc4fd-117">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="cc4fd-117">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="cc4fd-118">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="cc4fd-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
