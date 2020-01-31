---
title: 'Метод ICorDebugCode4:: Енумератевариаблехомес'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: ca452b230e2508f2d69c9aa38f274db506f3a906
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784091"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="d003c-102">Метод ICorDebugCode4:: Енумератевариаблехомес</span><span class="sxs-lookup"><span data-stu-id="d003c-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="d003c-103">Возвращает перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="d003c-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d003c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d003c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d003c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d003c-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="d003c-106">Указатель на адрес объекта интерфейса [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) , который является перечислителем для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="d003c-106">A pointer to the address of an [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d003c-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="d003c-107">Remarks</span></span>  
 <span data-ttu-id="d003c-108">Объект интерфейса [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) является стандартным перечислителем, производным от интерфейса "ICorDebugEnum", который позволяет перечислить объекты [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d003c-108">The [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="d003c-109">Коллекция может содержать несколько объектов [ICorDebugVariableHome](icordebugvariablehome-interface.md) для одного и того же индекса слота или аргумента, если они имеют разные расположения в разных точках функции.</span><span class="sxs-lookup"><span data-stu-id="d003c-109">The collection may include multiple [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d003c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d003c-110">Requirements</span></span>  
 <span data-ttu-id="d003c-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d003c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d003c-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d003c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d003c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d003c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d003c-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d003c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d003c-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="d003c-115">See also</span></span>

- [<span data-ttu-id="d003c-116">Интерфейс ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="d003c-116">ICorDebugCode4 Interface</span></span>](icordebugcode4-interface.md)
- [<span data-ttu-id="d003c-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d003c-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
