---
title: "Метод ICorProfilerInfo2::GetStringLayout"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1ad91829fab31b47a1dd51bb6cc9118c2ebe4c3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="2d319-102">Метод ICorProfilerInfo2::GetStringLayout</span><span class="sxs-lookup"><span data-stu-id="2d319-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="2d319-103">Получает сведения о структуре строкового объекта.</span><span class="sxs-lookup"><span data-stu-id="2d319-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="2d319-104">Этот метод является устаревшим в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]и заменяется [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="2d319-104">This method is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d319-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d319-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d319-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2d319-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="2d319-107">[out] Указатель на расположение относительно смещение `ObjectID` указатель, в которой хранится длина строки.</span><span class="sxs-lookup"><span data-stu-id="2d319-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="2d319-108">Длина хранится в виде `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="2d319-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d319-109">Этот параметр Возвращает длину самой строки, а не длину буфера.</span><span class="sxs-lookup"><span data-stu-id="2d319-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="2d319-110">Длина буфера больше не доступен.</span><span class="sxs-lookup"><span data-stu-id="2d319-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="2d319-111">[out] Указатель на расположение относительно смещение `ObjectID` указатель, в которой хранится Длина самой строки.</span><span class="sxs-lookup"><span data-stu-id="2d319-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="2d319-112">Длина хранится в виде `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="2d319-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="2d319-113">[out] Указатель на смещение буфера относительно `ObjectID` указатель, который сохраняет строку расширенных символов.</span><span class="sxs-lookup"><span data-stu-id="2d319-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d319-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="2d319-114">Remarks</span></span>  
 <span data-ttu-id="2d319-115">`GetStringLayout` Метод получает смещения, относительно `ObjectID` указатель расположений, в которых хранятся следующие:</span><span class="sxs-lookup"><span data-stu-id="2d319-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
-   <span data-ttu-id="2d319-116">Длина буфера строки.</span><span class="sxs-lookup"><span data-stu-id="2d319-116">The length of the string's buffer.</span></span>  
  
-   <span data-ttu-id="2d319-117">Длина самой строки.</span><span class="sxs-lookup"><span data-stu-id="2d319-117">The length of the string itself.</span></span>  
  
-   <span data-ttu-id="2d319-118">Буфер, содержащий фактический строку расширенных символов.</span><span class="sxs-lookup"><span data-stu-id="2d319-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="2d319-119">Строки могут заканчиваться символом null.</span><span class="sxs-lookup"><span data-stu-id="2d319-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d319-120">Требования</span><span class="sxs-lookup"><span data-stu-id="2d319-120">Requirements</span></span>  
 <span data-ttu-id="2d319-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d319-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d319-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d319-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d319-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d319-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d319-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d319-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d319-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2d319-125">See Also</span></span>  
 [<span data-ttu-id="2d319-126">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="2d319-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="2d319-127">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="2d319-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
