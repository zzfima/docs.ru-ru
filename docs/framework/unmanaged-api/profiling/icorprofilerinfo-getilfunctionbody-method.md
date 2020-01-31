---
title: Метод ICorProfilerInfo::GetILFunctionBody
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
ms.openlocfilehash: 8160bb5b9ca5e0a4e22a1a831e978eaf125e7605
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870496"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="38ac4-102">Метод ICorProfilerInfo::GetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="38ac4-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="38ac4-103">Возвращает указатель на тело метода в коде на языке MSIL, начиная с его заголовка.</span><span class="sxs-lookup"><span data-stu-id="38ac4-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38ac4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38ac4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38ac4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="38ac4-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="38ac4-106">окне Идентификатор модуля, в котором находится функция.</span><span class="sxs-lookup"><span data-stu-id="38ac4-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="38ac4-107">окне Токен метаданных для метода.</span><span class="sxs-lookup"><span data-stu-id="38ac4-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="38ac4-108">заполняет Указатель на заголовок метода.</span><span class="sxs-lookup"><span data-stu-id="38ac4-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="38ac4-109">заполняет Целое число, указывающее размер метода.</span><span class="sxs-lookup"><span data-stu-id="38ac4-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38ac4-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="38ac4-110">Remarks</span></span>  
 <span data-ttu-id="38ac4-111">Метод ограничивается модулем, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="38ac4-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="38ac4-112">Поскольку метод `GetILFunctionBody` предназначен для предоставления средству доступа к коду MSIL до того, как он будет загружен средой CLR, он использует маркер метаданных метода для поиска нужного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="38ac4-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="38ac4-113">`GetILFunctionBody` может возвращать CORPROF_E_FUNCTION_NOT_IL HRESULT, если `methodId` указывает на метод без какого-либо кода MSIL (например, абстрактный метод или метод вызова платформы).</span><span class="sxs-lookup"><span data-stu-id="38ac4-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38ac4-114">Требования</span><span class="sxs-lookup"><span data-stu-id="38ac4-114">Requirements</span></span>  
 <span data-ttu-id="38ac4-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38ac4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38ac4-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="38ac4-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="38ac4-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38ac4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38ac4-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38ac4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38ac4-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="38ac4-119">See also</span></span>

- [<span data-ttu-id="38ac4-120">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="38ac4-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
