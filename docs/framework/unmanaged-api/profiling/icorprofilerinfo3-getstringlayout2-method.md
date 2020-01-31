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
ms.openlocfilehash: f3727343755d7014202f844be28414d31ce55bc1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862260"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="1377d-102">Метод ICorProfilerInfo3::GetStringLayout2</span><span class="sxs-lookup"><span data-stu-id="1377d-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="1377d-103">Получает сведения о структуре строкового объекта.</span><span class="sxs-lookup"><span data-stu-id="1377d-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="1377d-104">Этот метод заменяет метод [ICorProfilerInfo2:: GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1377d-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1377d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1377d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1377d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1377d-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="1377d-107">заполняет Указатель на смещение расположения относительно указателя `ObjectID`, в котором хранится длина строки.</span><span class="sxs-lookup"><span data-stu-id="1377d-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="1377d-108">Длина хранится в виде `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="1377d-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="1377d-109">заполняет Указатель на смещение буфера относительно указателя на `ObjectID`, в котором хранится строка расширенных символов.</span><span class="sxs-lookup"><span data-stu-id="1377d-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1377d-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="1377d-110">Remarks</span></span>  
 <span data-ttu-id="1377d-111">Строки могут завершаться или не заканчиваться нулем.</span><span class="sxs-lookup"><span data-stu-id="1377d-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1377d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1377d-112">Requirements</span></span>  
 <span data-ttu-id="1377d-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1377d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1377d-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1377d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1377d-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1377d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1377d-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1377d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1377d-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="1377d-117">See also</span></span>

- [<span data-ttu-id="1377d-118">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="1377d-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="1377d-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="1377d-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
