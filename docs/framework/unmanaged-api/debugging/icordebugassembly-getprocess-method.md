---
title: Метод ICorDebugAssembly::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1c3bcc0ed22fa970d92e2384277d0786016db19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402113"
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="4ebf5-102">Метод ICorDebugAssembly::GetProcess</span><span class="sxs-lookup"><span data-stu-id="4ebf5-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="4ebf5-103">Получает указатель интерфейса на процесс, в котором выполняется данный экземпляр ICorDebugAssembly.</span><span class="sxs-lookup"><span data-stu-id="4ebf5-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ebf5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ebf5-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ebf5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ebf5-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="4ebf5-106">[out] Указатель на интерфейс ICorDebugProcess, представляет собой процесс.</span><span class="sxs-lookup"><span data-stu-id="4ebf5-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ebf5-107">Требования</span><span class="sxs-lookup"><span data-stu-id="4ebf5-107">Requirements</span></span>  
 <span data-ttu-id="4ebf5-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ebf5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ebf5-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ebf5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ebf5-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ebf5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ebf5-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ebf5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
