---
title: Метод ICorProfilerInfo3::GetStringLayout2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetStringLayout2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1ac724db000f84e37995a34e808d3df4b1e7a960
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765405"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="cc764-102">Метод ICorProfilerInfo3::GetStringLayout2</span><span class="sxs-lookup"><span data-stu-id="cc764-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="cc764-103">Получает сведения о структуре строкового объекта.</span><span class="sxs-lookup"><span data-stu-id="cc764-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="cc764-104">Этот метод заменяет [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="cc764-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc764-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc764-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc764-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc764-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="cc764-107">[out] Указатель на смещение расположения, относительно `ObjectID` указатель, который хранит длину строки, сам.</span><span class="sxs-lookup"><span data-stu-id="cc764-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="cc764-108">Длина хранится в виде `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="cc764-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="cc764-109">[out] Указатель на смещение буфера, относительно `ObjectID` указатель, который сохраняет строку расширенных символов.</span><span class="sxs-lookup"><span data-stu-id="cc764-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc764-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc764-110">Remarks</span></span>  
 <span data-ttu-id="cc764-111">Строки могут или не может быть нулем.</span><span class="sxs-lookup"><span data-stu-id="cc764-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc764-112">Требования</span><span class="sxs-lookup"><span data-stu-id="cc764-112">Requirements</span></span>  
 <span data-ttu-id="cc764-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc764-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc764-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cc764-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cc764-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc764-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc764-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc764-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc764-117">См. также</span><span class="sxs-lookup"><span data-stu-id="cc764-117">See also</span></span>

- [<span data-ttu-id="cc764-118">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="cc764-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="cc764-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="cc764-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
