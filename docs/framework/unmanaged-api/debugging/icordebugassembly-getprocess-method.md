---
title: "Метод ICorDebugAssembly::GetProcess"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9250356bd1ab164ee293e6e86543108808d8d65a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="7cc15-102">Метод ICorDebugAssembly::GetProcess</span><span class="sxs-lookup"><span data-stu-id="7cc15-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="7cc15-103">Получает указатель интерфейса на процесс, в котором выполняется данный экземпляр ICorDebugAssembly.</span><span class="sxs-lookup"><span data-stu-id="7cc15-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cc15-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7cc15-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7cc15-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7cc15-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="7cc15-106">[out] Указатель на интерфейс ICorDebugProcess, представляет собой процесс.</span><span class="sxs-lookup"><span data-stu-id="7cc15-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cc15-107">Требования</span><span class="sxs-lookup"><span data-stu-id="7cc15-107">Requirements</span></span>  
 <span data-ttu-id="7cc15-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cc15-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cc15-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7cc15-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7cc15-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cc15-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cc15-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cc15-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
