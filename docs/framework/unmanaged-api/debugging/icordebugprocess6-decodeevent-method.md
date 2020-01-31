---
title: Метод ICorDebugProcess6::DecodeEvent
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: be30b1ff79c2aceb97eb4ad42052da7dd162f5d3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792288"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="1f893-102">Метод ICorDebugProcess6::DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="1f893-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="1f893-103">Декодирует события управляемой отладки, которые были инкапсулированы в полезную нагрузку из событий отладки специально созданных собственных исключений.</span><span class="sxs-lookup"><span data-stu-id="1f893-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f893-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f893-104">Syntax</span></span>  
  
```cpp  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f893-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f893-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="1f893-106">[входной] Указатель на массив байтов из события отладки собственного исключения, содержащий данные о событии управляемой отладки.</span><span class="sxs-lookup"><span data-stu-id="1f893-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="1f893-107">[входной] Количество элементов в массиве байтов `pRecord`.</span><span class="sxs-lookup"><span data-stu-id="1f893-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="1f893-108">окне Элемент перечисления [кордебугрекордформат](cordebugrecordformat-enumeration.md) , указывающий формат неуправляемого события отладки.</span><span class="sxs-lookup"><span data-stu-id="1f893-108">[in] A [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1f893-109">[входной] Битовое поле, которое зависит от целевой архитектуры и содержит дополнительные сведения о событии отладки.</span><span class="sxs-lookup"><span data-stu-id="1f893-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="1f893-110">Для систем Windows он может быть членом перечисления [кордебугдекодивентфлагсвиндовс](cordebugdecodeeventflagswindows-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="1f893-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="1f893-111">[входной] Идентификатор операционной системы для потока, в котором возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="1f893-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="1f893-112">заполняет Указатель на адрес объекта [ICorDebugDebugEvent](icordebugdebugevent-interface.md) , который представляет декодированное управляемое событие отладки.</span><span class="sxs-lookup"><span data-stu-id="1f893-112">[out] A pointer to the address of an [ICorDebugDebugEvent](icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f893-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="1f893-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f893-114">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="1f893-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f893-115">Требования</span><span class="sxs-lookup"><span data-stu-id="1f893-115">Requirements</span></span>  
 <span data-ttu-id="1f893-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f893-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f893-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f893-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f893-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f893-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f893-119">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f893-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f893-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="1f893-120">See also</span></span>

- [<span data-ttu-id="1f893-121">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="1f893-121">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="1f893-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1f893-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
