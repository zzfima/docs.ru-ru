---
title: "Метод ICorDebugFrame::GetCode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetCode
helpviewer_keywords:
- GetCode method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCode method [.NET Framework debugging]
ms.assetid: fbaa0794-a031-4015-8beb-2749e47ac340
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e4538526f0358e7fa5259e87cbdf46abdb662475
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="2bcb2-102">Метод ICorDebugFrame::GetCode</span><span class="sxs-lookup"><span data-stu-id="2bcb2-102">ICorDebugFrame::GetCode Method</span></span>
<span data-ttu-id="2bcb2-103">Возвращает указатель на код, связанный с данным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bcb2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2bcb2-104">Syntax</span></span>  
  
```  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2bcb2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2bcb2-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="2bcb2-106">[out] Указатель на адрес объекта ICorDebugCode, который представляет код, связанный с данным кадром.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bcb2-107">Требования</span><span class="sxs-lookup"><span data-stu-id="2bcb2-107">Requirements</span></span>  
 <span data-ttu-id="2bcb2-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bcb2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bcb2-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2bcb2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bcb2-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bcb2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bcb2-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bcb2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
