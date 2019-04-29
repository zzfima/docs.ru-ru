---
title: Метод ICorDebugProcess::IsTransitionStub
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18084cb69d2c620fc892cc05e5a561e8fda3bc1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775524"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="95006-102">Метод ICorDebugProcess::IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="95006-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="95006-103">Получает значение, указывающее, является ли адрес в заглушке, вызовет переход к управляемому коду.</span><span class="sxs-lookup"><span data-stu-id="95006-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95006-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95006-104">Syntax</span></span>  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95006-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="95006-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="95006-106">[in] Объект `CORDB_ADDRESS` значение, указывающее адрес в вопросе.</span><span class="sxs-lookup"><span data-stu-id="95006-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="95006-107">[out] Указатель на логическое значение, которое является `true` Если указанный адрес находится внутри заглушку, вызовет переход к управляемому коду; в противном случае \*`pbTransitionStub` является `false`.</span><span class="sxs-lookup"><span data-stu-id="95006-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95006-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="95006-108">Remarks</span></span>  
 <span data-ttu-id="95006-109">`IsTransitionStub` Метод может использоваться в неуправляемом коде пошагового выполнения для принятия решения о возвращения управления пошаговым управляемый шаг.</span><span class="sxs-lookup"><span data-stu-id="95006-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="95006-110">Вы также можете заглушки перехода удостоверений, просмотрев сведения в переносимый исполняемый файл (PE).</span><span class="sxs-lookup"><span data-stu-id="95006-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95006-111">Требования</span><span class="sxs-lookup"><span data-stu-id="95006-111">Requirements</span></span>  
 <span data-ttu-id="95006-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95006-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95006-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95006-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95006-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95006-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95006-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95006-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
