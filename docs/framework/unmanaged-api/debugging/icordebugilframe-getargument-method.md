---
title: "Метод ICorDebugILFrame::GetArgument"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.GetArgument
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c6b1c097d830af4e68035f79670983002c15c16d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="5bcd8-102">Метод ICorDebugILFrame::GetArgument</span><span class="sxs-lookup"><span data-stu-id="5bcd8-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="5bcd8-103">Возвращает значение указанного аргумента в кадре стека промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bcd8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bcd8-104">Syntax</span></span>  
  
```  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5bcd8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5bcd8-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="5bcd8-106">[in] Индекс аргумента в кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="5bcd8-107">[out] Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение.</span><span class="sxs-lookup"><span data-stu-id="5bcd8-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bcd8-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5bcd8-108">Remarks</span></span>  
 <span data-ttu-id="5bcd8-109">`GetArgument` Метод может использоваться в кадре стека MSIL или в кадре скомпилированных just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="5bcd8-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bcd8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5bcd8-110">Requirements</span></span>  
 <span data-ttu-id="5bcd8-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bcd8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bcd8-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5bcd8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bcd8-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bcd8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bcd8-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bcd8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
