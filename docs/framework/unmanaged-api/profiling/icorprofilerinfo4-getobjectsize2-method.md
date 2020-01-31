---
title: Метод ICorProfilerInfo4::GetObjectSize2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
ms.openlocfilehash: 441f7743ba01884592393ce9382348fbecaeaa9d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861883"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="52a32-102">Метод ICorProfilerInfo4::GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="52a32-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="52a32-103">Возвращает размер указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="52a32-103">Returns the size of a specified object.</span></span> <span data-ttu-id="52a32-104">Заменяет метод [ICorProfilerInfo:: жетобжектсизе](icorprofilerinfo-getobjectsize-method.md) , сообщая размеры объектов, размер которых больше, чем может быть выражено в `ULONG`.</span><span class="sxs-lookup"><span data-stu-id="52a32-104">Replaces the [ICorProfilerInfo::GetObjectSize](icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52a32-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52a32-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52a32-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="52a32-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="52a32-107">окне Идентификатор объекта.</span><span class="sxs-lookup"><span data-stu-id="52a32-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="52a32-108">заполняет Указатель на размер объекта в байтах.</span><span class="sxs-lookup"><span data-stu-id="52a32-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52a32-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="52a32-109">Remarks</span></span>  
 <span data-ttu-id="52a32-110">Различные объекты одних и тех же типов часто имеют одинаковый размер.</span><span class="sxs-lookup"><span data-stu-id="52a32-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="52a32-111">Однако некоторые типы, такие как массивы или строки, могут иметь разные размеры для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="52a32-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52a32-112">Требования</span><span class="sxs-lookup"><span data-stu-id="52a32-112">Requirements</span></span>  
 <span data-ttu-id="52a32-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52a32-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52a32-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52a32-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52a32-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52a32-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52a32-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52a32-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52a32-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="52a32-117">See also</span></span>

- [<span data-ttu-id="52a32-118">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="52a32-118">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
