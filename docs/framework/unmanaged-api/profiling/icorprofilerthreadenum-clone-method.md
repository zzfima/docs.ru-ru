---
title: Метод ICorProfilerThreadEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
ms.openlocfilehash: 9048d314404859a4264621a5da91c43c525027f9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868204"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="d6863-102">Метод ICorProfilerThreadEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="d6863-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="d6863-103">Получает указатель интерфейса на копию этого интерфейса [икорпрофилерсреаденум](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d6863-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6863-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6863-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6863-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d6863-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="d6863-106">заполняет Указатель на указатель интерфейса, который, в свою очередь, указывает на копию этого интерфейса [икорпрофилерсреаденум](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d6863-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="d6863-107">Копия перечислителя поддерживает собственное состояние перечисления отдельно от этого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="d6863-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="d6863-108">Однако начальная координата курсора копирования совпадает с текущей позицией курсора в перечислителе.</span><span class="sxs-lookup"><span data-stu-id="d6863-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6863-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d6863-109">Requirements</span></span>  
 <span data-ttu-id="d6863-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6863-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6863-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d6863-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d6863-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6863-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6863-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6863-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6863-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="d6863-114">See also</span></span>

- [<span data-ttu-id="d6863-115">икорпрофилерсреаденум</span><span class="sxs-lookup"><span data-stu-id="d6863-115">ICorProfilerThreadEnum</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="d6863-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="d6863-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
