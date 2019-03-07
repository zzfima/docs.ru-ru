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
ms.openlocfilehash: fdfa6f5cb5aae2124f04580ce49064ba857e2602
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473036"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="52101-102">Метод ICorProfilerInfo2::GetStringLayout</span><span class="sxs-lookup"><span data-stu-id="52101-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="52101-103">Получает сведения о структуре строкового объекта.</span><span class="sxs-lookup"><span data-stu-id="52101-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="52101-104">Этот метод является устаревшим в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]и заменяется [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="52101-104">This method is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52101-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52101-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52101-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="52101-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="52101-107">[out] Указатель на смещение расположения, относительно `ObjectID` указатель, который хранит длину строки.</span><span class="sxs-lookup"><span data-stu-id="52101-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="52101-108">Длина хранится в виде `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="52101-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52101-109">Этот параметр Возвращает длину самой строки, а не длину буфера.</span><span class="sxs-lookup"><span data-stu-id="52101-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="52101-110">Длина буфера больше недоступен.</span><span class="sxs-lookup"><span data-stu-id="52101-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="52101-111">[out] Указатель на смещение расположения, относительно `ObjectID` указатель, который хранит длину строки, сам.</span><span class="sxs-lookup"><span data-stu-id="52101-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="52101-112">Длина хранится в виде `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="52101-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="52101-113">[out] Указатель на смещение буфера, относительно `ObjectID` указатель, в котором хранится строка расширенных символов.</span><span class="sxs-lookup"><span data-stu-id="52101-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52101-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="52101-114">Remarks</span></span>  
 <span data-ttu-id="52101-115">`GetStringLayout` Метод получает смещения, относительно `ObjectID` указатель из расположений, в которых хранятся следующие:</span><span class="sxs-lookup"><span data-stu-id="52101-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
-   <span data-ttu-id="52101-116">Длина буфера строки.</span><span class="sxs-lookup"><span data-stu-id="52101-116">The length of the string's buffer.</span></span>  
  
-   <span data-ttu-id="52101-117">Длина самой строки.</span><span class="sxs-lookup"><span data-stu-id="52101-117">The length of the string itself.</span></span>  
  
-   <span data-ttu-id="52101-118">Буфер, содержащий фактический строку расширенных символов.</span><span class="sxs-lookup"><span data-stu-id="52101-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="52101-119">Строки могут представлять собой нулем.</span><span class="sxs-lookup"><span data-stu-id="52101-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52101-120">Требования</span><span class="sxs-lookup"><span data-stu-id="52101-120">Requirements</span></span>  
 <span data-ttu-id="52101-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52101-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52101-122">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52101-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52101-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52101-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52101-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52101-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52101-125">См. также</span><span class="sxs-lookup"><span data-stu-id="52101-125">See also</span></span>
- [<span data-ttu-id="52101-126">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="52101-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="52101-127">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="52101-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
