---
title: Метод ICorDebugModule2::GetJITCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.GetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::GetJITCompilerFlags
helpviewer_keywords:
- GetJITCompilerFlags method [.NET Framework debugging]
- ICorDebugModule2::GetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: 7212d9f4-989b-44e3-b8d4-ffc35922f6a0
topic_type:
- apiref
ms.openlocfilehash: ab6551ba70ed4cd154b166eeb92138b6550d2cb2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792968"
---
# <a name="icordebugmodule2getjitcompilerflags-method"></a><span data-ttu-id="9ae18-102">Метод ICorDebugModule2::GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="9ae18-102">ICorDebugModule2::GetJITCompilerFlags Method</span></span>
<span data-ttu-id="9ae18-103">Возвращает флаги, управляющие JIT-компиляцией этого ICorDebugModule2.</span><span class="sxs-lookup"><span data-stu-id="9ae18-103">Gets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ae18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ae18-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJITCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ae18-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ae18-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="9ae18-106">заполняет Указатель на значение перечисления [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) , которое управляет JIT-компиляцией.</span><span class="sxs-lookup"><span data-stu-id="9ae18-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that controls the JIT compilation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ae18-107">Требования</span><span class="sxs-lookup"><span data-stu-id="9ae18-107">Requirements</span></span>  
 <span data-ttu-id="9ae18-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ae18-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ae18-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ae18-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ae18-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ae18-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ae18-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ae18-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
