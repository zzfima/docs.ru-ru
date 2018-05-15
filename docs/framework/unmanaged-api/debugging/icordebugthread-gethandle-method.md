---
title: Метод ICorDebugThread::GetHandle
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 358597edc9fbc5203e5c00a5fb4d04019281060d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="ec808-102">Метод ICorDebugThread::GetHandle</span><span class="sxs-lookup"><span data-stu-id="ec808-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="ec808-103">Возвращает текущий дескриптор для активной части ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="ec808-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec808-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec808-104">Syntax</span></span>  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec808-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec808-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="ec808-106">[out] Указатель на HTHREAD, который представляет собой дескриптор активной части данного потока.</span><span class="sxs-lookup"><span data-stu-id="ec808-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec808-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ec808-107">Remarks</span></span>  
 <span data-ttu-id="ec808-108">Дескриптор может меняться, поскольку процесс выполняется и может быть разным для разных частей потока.</span><span class="sxs-lookup"><span data-stu-id="ec808-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="ec808-109">Этот дескриптор принадлежит API отладки.</span><span class="sxs-lookup"><span data-stu-id="ec808-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="ec808-110">Отладчик должен его скопировать перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="ec808-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec808-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ec808-111">Requirements</span></span>  
 <span data-ttu-id="ec808-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec808-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec808-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec808-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec808-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec808-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec808-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec808-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
