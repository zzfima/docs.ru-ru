---
title: "Метод ICorDebugVariableHome::GetOffset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ddedc83e4e51cf12a3f8a0504d90bda7f944a6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="32eaa-102">Метод ICorDebugVariableHome::GetOffset</span><span class="sxs-lookup"><span data-stu-id="32eaa-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="32eaa-103">Получает смещение от базового регистра для переменной.</span><span class="sxs-lookup"><span data-stu-id="32eaa-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32eaa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32eaa-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32eaa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="32eaa-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="32eaa-106">[out] Смещение от базового регистра.</span><span class="sxs-lookup"><span data-stu-id="32eaa-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32eaa-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="32eaa-107">Return Value</span></span>  
 <span data-ttu-id="32eaa-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="32eaa-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="32eaa-109">Значение</span><span class="sxs-lookup"><span data-stu-id="32eaa-109">Value</span></span>|<span data-ttu-id="32eaa-110">Описание</span><span class="sxs-lookup"><span data-stu-id="32eaa-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="32eaa-111">Переменная находится в расположении относительно регистра памяти.</span><span class="sxs-lookup"><span data-stu-id="32eaa-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="32eaa-112">Переменная не существует в расположении относительно регистра памяти.</span><span class="sxs-lookup"><span data-stu-id="32eaa-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="32eaa-113">Требования</span><span class="sxs-lookup"><span data-stu-id="32eaa-113">Requirements</span></span>  
 <span data-ttu-id="32eaa-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32eaa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32eaa-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32eaa-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32eaa-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32eaa-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32eaa-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32eaa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32eaa-118">См. также</span><span class="sxs-lookup"><span data-stu-id="32eaa-118">See Also</span></span>  
 [<span data-ttu-id="32eaa-119">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="32eaa-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
