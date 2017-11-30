---
title: "Метод ICorDebugThread::GetProcess"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: be58714856b93a244248fb97d6cc1e1b4ec476c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="e8590-102">Метод ICorDebugThread::GetProcess</span><span class="sxs-lookup"><span data-stu-id="e8590-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="e8590-103">Возвращает указатель на интерфейс для процесса, из которых ICorDebugThread эти формы.</span><span class="sxs-lookup"><span data-stu-id="e8590-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8590-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8590-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8590-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e8590-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="e8590-106">[out] Указатель на адрес объекта интерфейса ICorDebugProcess, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="e8590-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8590-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e8590-107">Requirements</span></span>  
 <span data-ttu-id="e8590-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8590-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8590-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8590-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8590-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8590-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8590-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8590-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
