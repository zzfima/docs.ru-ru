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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bde194023ff6913db9a56e30eddaad8d7abc5ad1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452811"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="5235d-102">Метод ICorProfilerInfo::GetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="5235d-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="5235d-103">Возвращает указатель на основной части метода в код MSIL (MSIL), начиная с его заголовка.</span><span class="sxs-lookup"><span data-stu-id="5235d-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5235d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5235d-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5235d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5235d-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="5235d-106">[in] Идентификатор модуля, в которой находится функция.</span><span class="sxs-lookup"><span data-stu-id="5235d-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="5235d-107">[in] Токен метаданных для метода.</span><span class="sxs-lookup"><span data-stu-id="5235d-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="5235d-108">[out] Указатель на метод заголовок.</span><span class="sxs-lookup"><span data-stu-id="5235d-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="5235d-109">[out] Целое число, указывающее размер метода.</span><span class="sxs-lookup"><span data-stu-id="5235d-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5235d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="5235d-110">Remarks</span></span>  
 <span data-ttu-id="5235d-111">Метод действует в модуле, в которой они находятся.</span><span class="sxs-lookup"><span data-stu-id="5235d-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="5235d-112">Поскольку `GetILFunctionBody` метод предназначен для предоставления доступа в MSIL-код, прежде чем он будет загружен с общеязыковой среды выполнения (CLR), он использует токен метаданных метода для поиска к нужному экземпляру.</span><span class="sxs-lookup"><span data-stu-id="5235d-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="5235d-113">`GetILFunctionBody` Можно также вернуть CORPROF_E_FUNCTION_NOT_IL HRESULT Если `methodId` указывает на метод без любой MSIL кода (таких как абстрактный метод или для платформы, вызовите метод (PInvoke)).</span><span class="sxs-lookup"><span data-stu-id="5235d-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5235d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5235d-114">Requirements</span></span>  
 <span data-ttu-id="5235d-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5235d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5235d-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5235d-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5235d-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5235d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5235d-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5235d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5235d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5235d-119">See Also</span></span>  
 [<span data-ttu-id="5235d-120">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="5235d-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
