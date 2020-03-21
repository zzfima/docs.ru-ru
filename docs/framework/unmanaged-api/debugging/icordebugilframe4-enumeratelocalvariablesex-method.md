---
title: Метод ICorDebugILFrame4::EnumerateLocalVariablesEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type:
- apiref
ms.openlocfilehash: 341a86f4c1c8367f979e193a6284bf89f1b03ca0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178805"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="25b72-102">Метод ICorDebugILFrame4::EnumerateLocalVariablesEx</span><span class="sxs-lookup"><span data-stu-id="25b72-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>
<span data-ttu-id="25b72-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="25b72-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="25b72-104">Получает перечислитель для локальной переменной в кадре и может включать переменные, добавленные в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="25b72-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25b72-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25b72-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25b72-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="25b72-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="25b72-107">(в) Член [пересчета ILCodeKind,](ilcodekind-enumeration.md) который определяет, включены ли в кадр переменные, добавленные в инструменты профайлера ReJIT.</span><span class="sxs-lookup"><span data-stu-id="25b72-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="25b72-108">(ваут) Указатель на адрес объекта "ICorDebugValueEnum", который является регистратором локальных переменных в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="25b72-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25b72-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="25b72-109">Remarks</span></span>  
 <span data-ttu-id="25b72-110">Этот метод аналогичен методу [EnumerateLocalVariables,](icordebugilframe-enumeratelocalvariables-method.md) за исключением того, что он дополнительно получает доступ к переменным, добавленным в инструментарий ReJIT.</span><span class="sxs-lookup"><span data-stu-id="25b72-110">This method is similar to the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="25b72-111">Установка `flags` `ILCODE_ORIGINAL_IL` эквивалентна вызову [ICorDebugILFrame::EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md).</span><span class="sxs-lookup"><span data-stu-id="25b72-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="25b72-112">Установка значения `flags` для параметра `ILCODE_REJIT_IL` позволяет отладчику получить доступ к локальным переменным, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="25b72-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="25b72-113">Если промежуточный язык не инструментирован, перечисление будет пустым, а метод вернет значение `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="25b72-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="25b72-114">Перечислитель может не включать все локальные переменные выполняемого метода, так как некоторые из них могут быть неактивными.</span><span class="sxs-lookup"><span data-stu-id="25b72-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25b72-115">Требования</span><span class="sxs-lookup"><span data-stu-id="25b72-115">Requirements</span></span>  
 <span data-ttu-id="25b72-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25b72-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25b72-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25b72-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25b72-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25b72-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25b72-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25b72-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25b72-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="25b72-120">See also</span></span>

- [<span data-ttu-id="25b72-121">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="25b72-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="25b72-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="25b72-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="25b72-123">ReJIT: Как-к руководству</span><span class="sxs-lookup"><span data-stu-id="25b72-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
