---
title: Метод ICorProfilerObjectEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type:
- apiref
ms.openlocfilehash: a1a616c1289867864eb9eb449c7d6f47f9a8352b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861298"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="c7759-102">Метод ICorProfilerObjectEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="c7759-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="c7759-103">Возвращает общее число замороженных объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="c7759-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7759-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7759-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7759-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7759-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="c7759-106">заполняет Указатель на число замороженных объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="c7759-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="c7759-107">Этот метод всегда будет возвращать ноль в .NET Framework версии 3,5 с пакетом обновления 1 (SP1) и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="c7759-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7759-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c7759-108">Requirements</span></span>  
 <span data-ttu-id="c7759-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7759-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7759-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c7759-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c7759-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7759-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7759-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7759-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7759-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="c7759-113">See also</span></span>

- [<span data-ttu-id="c7759-114">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="c7759-114">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
