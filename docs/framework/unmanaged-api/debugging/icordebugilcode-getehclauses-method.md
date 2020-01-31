---
title: Метод ICorDebugILCode::GetEHClauses
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode.GetEHClauses
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type:
- apiref
ms.openlocfilehash: ac9a4e4b54b302afeae4ede1dd574c15ded3ff12
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788603"
---
# <a name="icordebugilcodegetehclauses-method"></a><span data-ttu-id="6a148-102">Метод ICorDebugILCode::GetEHClauses</span><span class="sxs-lookup"><span data-stu-id="6a148-102">ICorDebugILCode::GetEHClauses Method</span></span>
<span data-ttu-id="6a148-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="6a148-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="6a148-104">Возвращает указатель на список предложений обработки исключений, определенных для этого промежуточного языка.</span><span class="sxs-lookup"><span data-stu-id="6a148-104">Returns a pointer to a list of exception handling (EH) clauses that are defined for this intermediate language (IL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a148-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a148-105">Syntax</span></span>  
  
```cpp
HRESULT GetEHClauses(  
   [in] ULONG32 cClauses,  
   [out] ULONG32 * pcClauses,  
   [out, size_is(cClauses), length_is(*pcClauses)] CorDebugEHClause clauses[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a148-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6a148-106">Parameters</span></span>  
 `cClauses`  
 <span data-ttu-id="6a148-107">[в] Емкость хранилища массива `clauses`.</span><span class="sxs-lookup"><span data-stu-id="6a148-107">[in] The storage capacity of the `clauses` array.</span></span> <span data-ttu-id="6a148-108">Дополнительные сведения см. в разделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="6a148-108">See the Remarks section for more information.</span></span>  
  
 `pcClauses`  
 <span data-ttu-id="6a148-109">[из] Количество предложений, информация о которых записывается в массив `clauses`.</span><span class="sxs-lookup"><span data-stu-id="6a148-109">[out] The number of clauses about which information is written to the `clauses` array.</span></span>  
  
 <span data-ttu-id="6a148-110">предложения</span><span class="sxs-lookup"><span data-stu-id="6a148-110">clauses</span></span>  
 <span data-ttu-id="6a148-111">заполняет Массив объектов [кордебужехклаусе](cordebugehclause-structure.md) , содержащих сведения о предложениях обработки исключений, определенных для этого IL.</span><span class="sxs-lookup"><span data-stu-id="6a148-111">[out] An array of [CorDebugEHClause](cordebugehclause-structure.md) objects that contain information on exception handling clauses defined for this IL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a148-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="6a148-112">Remarks</span></span>  
 <span data-ttu-id="6a148-113">Если `cClauses` имеет значение 0, а `pcClauses` не равно**null**, `pcClauses` задается число доступных предложений обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="6a148-113">If `cClauses` is 0 and `pcClauses` is non-**null**, `pcClauses` is set to the number of available exception handling clauses.</span></span> <span data-ttu-id="6a148-114">Если значение `cClauses` не равно 0, оно обозначает емкость хранилища массива `clauses`.</span><span class="sxs-lookup"><span data-stu-id="6a148-114">If `cClauses` is non-zero, it represents the storage capacity of the `clauses` array.</span></span> <span data-ttu-id="6a148-115">Когда метод возвращает не пустое значение, `clauses` содержит максимум элементов `cClauses`, а значению `pcClauses` присваивается количество предложений, записанных в массив `clauses` на данный момент.</span><span class="sxs-lookup"><span data-stu-id="6a148-115">When the method returns, `clauses` contains a maximum of `cClauses` items, and `pcClauses` is set to the number of clauses actually written to the `clauses` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a148-116">Требования</span><span class="sxs-lookup"><span data-stu-id="6a148-116">Requirements</span></span>  
 <span data-ttu-id="6a148-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a148-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a148-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a148-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a148-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a148-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a148-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a148-120">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a148-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="6a148-121">See also</span></span>

- [<span data-ttu-id="6a148-122">Интерфейс ICorDebugILCode</span><span class="sxs-lookup"><span data-stu-id="6a148-122">ICorDebugILCode Interface</span></span>](icordebugilcode-interface.md)
- [<span data-ttu-id="6a148-123">Структура CorDebugEHClause</span><span class="sxs-lookup"><span data-stu-id="6a148-123">CorDebugEHClause Structure</span></span>](cordebugehclause-structure.md)
- [<span data-ttu-id="6a148-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6a148-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
