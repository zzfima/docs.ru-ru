---
title: Метод ICorProfilerInfo2::GetStringLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: faa5ecf63ac3795a58369d94f9fb15f853edb576
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490713"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="63d01-102">Метод ICorProfilerInfo2::GetStringLayout</span><span class="sxs-lookup"><span data-stu-id="63d01-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="63d01-103">Получает сведения о структуре строкового объекта.</span><span class="sxs-lookup"><span data-stu-id="63d01-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="63d01-104">Этот метод является устаревшим в .NET Framework 4 и заменяется [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="63d01-104">This method is deprecated in the .NET Framework 4, and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d01-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63d01-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63d01-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="63d01-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="63d01-107">[out] Указатель на смещение расположения, относительно `ObjectID` указатель, который хранит длину строки.</span><span class="sxs-lookup"><span data-stu-id="63d01-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="63d01-108">Длина хранится в виде `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="63d01-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63d01-109">Этот параметр Возвращает длину самой строки, а не длину буфера.</span><span class="sxs-lookup"><span data-stu-id="63d01-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="63d01-110">Длина буфера больше недоступен.</span><span class="sxs-lookup"><span data-stu-id="63d01-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="63d01-111">[out] Указатель на смещение расположения, относительно `ObjectID` указатель, который хранит длину строки, сам.</span><span class="sxs-lookup"><span data-stu-id="63d01-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="63d01-112">Длина хранится в виде `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="63d01-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="63d01-113">[out] Указатель на смещение буфера, относительно `ObjectID` указатель, в котором хранится строка расширенных символов.</span><span class="sxs-lookup"><span data-stu-id="63d01-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63d01-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="63d01-114">Remarks</span></span>  
 <span data-ttu-id="63d01-115">`GetStringLayout` Метод получает смещения, относительно `ObjectID` указатель из расположений, в которых хранятся следующие:</span><span class="sxs-lookup"><span data-stu-id="63d01-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="63d01-116">Длина буфера строки.</span><span class="sxs-lookup"><span data-stu-id="63d01-116">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="63d01-117">Длина самой строки.</span><span class="sxs-lookup"><span data-stu-id="63d01-117">The length of the string itself.</span></span>  
  
- <span data-ttu-id="63d01-118">Буфер, содержащий фактический строку расширенных символов.</span><span class="sxs-lookup"><span data-stu-id="63d01-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="63d01-119">Строки могут представлять собой нулем.</span><span class="sxs-lookup"><span data-stu-id="63d01-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63d01-120">Требования</span><span class="sxs-lookup"><span data-stu-id="63d01-120">Requirements</span></span>  
 <span data-ttu-id="63d01-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63d01-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d01-122">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="63d01-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="63d01-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63d01-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63d01-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63d01-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d01-125">См. также</span><span class="sxs-lookup"><span data-stu-id="63d01-125">See also</span></span>

- [<span data-ttu-id="63d01-126">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="63d01-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="63d01-127">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="63d01-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
