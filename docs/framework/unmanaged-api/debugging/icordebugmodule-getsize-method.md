---
title: Метод ICorDebugModule::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 540288f83de9c3c6ff2111330c77ded48abd6d5f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479121"
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="26ec2-102">Метод ICorDebugModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="26ec2-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="26ec2-103">Возвращает размер в байтах, модуля.</span><span class="sxs-lookup"><span data-stu-id="26ec2-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26ec2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26ec2-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26ec2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="26ec2-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="26ec2-106">[out] Размер модуля в байтах.</span><span class="sxs-lookup"><span data-stu-id="26ec2-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="26ec2-107">Если модуль был создан из генератора образов в машинном коде (NGen.exe), размер модуля будет ноль.</span><span class="sxs-lookup"><span data-stu-id="26ec2-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26ec2-108">Требования</span><span class="sxs-lookup"><span data-stu-id="26ec2-108">Requirements</span></span>  
 <span data-ttu-id="26ec2-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26ec2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26ec2-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26ec2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26ec2-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26ec2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26ec2-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26ec2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
