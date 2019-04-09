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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f9d20eda8684a9a5ae43c6240d0f8a9722c4d97
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076839"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="89412-102">Метод ICorDebugILFrame4::EnumerateLocalVariablesEx</span><span class="sxs-lookup"><span data-stu-id="89412-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>
<span data-ttu-id="89412-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="89412-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="89412-104">Получает перечислитель для локальной переменной в кадре и может включать переменные, добавленные в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="89412-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89412-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89412-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89412-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="89412-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="89412-107">[in] [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) член перечисления, указывающее, включаются ли в кадр переменным, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="89412-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="89412-108">[out] Указатель на адрес объекта «ICorDebugValueEnum», который является перечислителем для локальных переменных в кадре.</span><span class="sxs-lookup"><span data-stu-id="89412-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89412-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="89412-109">Remarks</span></span>  
 <span data-ttu-id="89412-110">Этот метод аналогичен методу [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) за тем исключением, что он дополнительно получает доступ к переменным, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="89412-110">This method is similar to the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="89412-111">Установка `flags` для `ILCODE_ORIGINAL_IL` эквивалентно вызову [ICorDebugILFrame::EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md).</span><span class="sxs-lookup"><span data-stu-id="89412-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="89412-112">Установка значения `flags` для параметра `ILCODE_REJIT_IL` позволяет отладчику получить доступ к локальным переменным, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="89412-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="89412-113">Если промежуточный язык не инструментирован, перечисление будет пустым, а метод вернет значение `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="89412-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="89412-114">Перечислитель может не включать все локальные переменные выполняемого метода, так как некоторые из них могут быть неактивными.</span><span class="sxs-lookup"><span data-stu-id="89412-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89412-115">Требования</span><span class="sxs-lookup"><span data-stu-id="89412-115">Requirements</span></span>  
 <span data-ttu-id="89412-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89412-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89412-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89412-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89412-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89412-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="89412-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="89412-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="89412-120">См. также</span><span class="sxs-lookup"><span data-stu-id="89412-120">See also</span></span>

- [<span data-ttu-id="89412-121">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="89412-121">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="89412-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="89412-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="89412-123">ReJIT: Практическое руководство</span><span class="sxs-lookup"><span data-stu-id="89412-123">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
