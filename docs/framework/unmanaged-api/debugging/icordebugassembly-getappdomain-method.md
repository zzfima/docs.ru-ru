---
title: "Метод ICorDebugAssembly::GetAppDomain"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly.GetAppDomain
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly::GetAppDomain
helpviewer_keywords:
- ICorDebugAssembly::GetAppDomain method [.NET Framework debugging]
- GetAppDomain method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 14e18510-23ac-4cba-9f96-c86147a2df9d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f97795568b9811d0dbf7852fd64d5256c29b8f30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="ca1dd-102">Метод ICorDebugAssembly::GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="ca1dd-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="ca1dd-103">Получает указатель интерфейса на домен приложения, который содержит это `ICorDebugAssembly` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ca1dd-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca1dd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca1dd-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca1dd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca1dd-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="ca1dd-106">[out] Указатель на адрес ICorDebugAppDomain-интерфейс, который представляет домен приложения.</span><span class="sxs-lookup"><span data-stu-id="ca1dd-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca1dd-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ca1dd-107">Remarks</span></span>  
 <span data-ttu-id="ca1dd-108">Если эта сборка является системную сборку `GetAppDomain` возвращает значение null.</span><span class="sxs-lookup"><span data-stu-id="ca1dd-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca1dd-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ca1dd-109">Requirements</span></span>  
 <span data-ttu-id="ca1dd-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca1dd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca1dd-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca1dd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca1dd-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca1dd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca1dd-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca1dd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
