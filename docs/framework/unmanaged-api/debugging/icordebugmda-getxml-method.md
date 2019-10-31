---
title: Метод ICorDebugMDA::GetXML
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
ms.openlocfilehash: f80bdffbf5c0ba39980bd27c6e89a368547340c0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129811"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="df165-102">Метод ICorDebugMDA::GetXML</span><span class="sxs-lookup"><span data-stu-id="df165-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="df165-103">Возвращает полный XML-поток, связанный с помощником по отладке управляемого кода (MDA), представленным [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="df165-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df165-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df165-104">Syntax</span></span>  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df165-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="df165-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="df165-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="df165-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="df165-107">заполняет Указатель на длину XML-потока.</span><span class="sxs-lookup"><span data-stu-id="df165-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="df165-108">заполняет Массив, в котором хранится XML-поток.</span><span class="sxs-lookup"><span data-stu-id="df165-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="df165-109">Массив может быть пустым.</span><span class="sxs-lookup"><span data-stu-id="df165-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df165-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="df165-110">Remarks</span></span>  
 <span data-ttu-id="df165-111">Метод `GetXML` потенциально может повлиять на производительность в зависимости от размера соответствующего потока XML.</span><span class="sxs-lookup"><span data-stu-id="df165-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df165-112">Требования</span><span class="sxs-lookup"><span data-stu-id="df165-112">Requirements</span></span>  
 <span data-ttu-id="df165-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df165-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df165-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df165-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df165-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df165-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df165-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df165-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df165-117">См. также</span><span class="sxs-lookup"><span data-stu-id="df165-117">See also</span></span>

- [<span data-ttu-id="df165-118">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="df165-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="df165-119">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="df165-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
