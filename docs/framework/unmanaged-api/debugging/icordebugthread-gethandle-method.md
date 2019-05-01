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
ms.openlocfilehash: 900fece1dd29f73f77b85ff08e4deff1396f8aaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994023"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="199b2-102">Метод ICorDebugThread::GetHandle</span><span class="sxs-lookup"><span data-stu-id="199b2-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="199b2-103">Получает текущий дескриптор для активной части ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="199b2-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="199b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="199b2-104">Syntax</span></span>  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="199b2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="199b2-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="199b2-106">[out] Указатель на HTHREAD, представляющую собой дескриптор активной части этого потока.</span><span class="sxs-lookup"><span data-stu-id="199b2-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="199b2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="199b2-107">Remarks</span></span>  
 <span data-ttu-id="199b2-108">Дескриптор может меняться, процесс выполнения, и может быть разным для разных частей потока.</span><span class="sxs-lookup"><span data-stu-id="199b2-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="199b2-109">Этот дескриптор является владельцем API отладки.</span><span class="sxs-lookup"><span data-stu-id="199b2-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="199b2-110">Отладчик должен его скопировать перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="199b2-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="199b2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="199b2-111">Requirements</span></span>  
 <span data-ttu-id="199b2-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="199b2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="199b2-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="199b2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="199b2-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="199b2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="199b2-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="199b2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
