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
ms.openlocfilehash: e0957228489df30833790e59da1ca597fc1f92f5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076511"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="a8917-102">Метод ICorProfilerInfo3::GetStringLayout2</span><span class="sxs-lookup"><span data-stu-id="a8917-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="a8917-103">Получает сведения о структуре строкового объекта.</span><span class="sxs-lookup"><span data-stu-id="a8917-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="a8917-104">Этот метод заменяет [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="a8917-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8917-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8917-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8917-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a8917-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="a8917-107">[out] Указатель на смещение расположения, относительно `ObjectID` указатель, который хранит длину строки, сам.</span><span class="sxs-lookup"><span data-stu-id="a8917-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="a8917-108">Длина хранится в виде `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="a8917-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="a8917-109">[out] Указатель на смещение буфера, относительно `ObjectID` указатель, который сохраняет строку расширенных символов.</span><span class="sxs-lookup"><span data-stu-id="a8917-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8917-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="a8917-110">Remarks</span></span>  
 <span data-ttu-id="a8917-111">Строки могут или не может быть нулем.</span><span class="sxs-lookup"><span data-stu-id="a8917-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8917-112">Требования</span><span class="sxs-lookup"><span data-stu-id="a8917-112">Requirements</span></span>  
 <span data-ttu-id="a8917-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8917-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8917-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a8917-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a8917-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8917-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a8917-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a8917-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a8917-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a8917-117">See also</span></span>

- [<span data-ttu-id="a8917-118">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="a8917-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="a8917-119">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="a8917-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
