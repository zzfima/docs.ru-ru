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
ms.openlocfilehash: b43548d18ac13ac30fa7b6c23699f1db98a78ca0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="f8827-102">Метод ICorDebugAssembly::GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="f8827-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="f8827-103">Получает указатель интерфейса на домен приложения, который содержит это `ICorDebugAssembly` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f8827-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8827-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8827-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8827-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8827-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="f8827-106">[out] Указатель на адрес ICorDebugAppDomain-интерфейс, который представляет домен приложения.</span><span class="sxs-lookup"><span data-stu-id="f8827-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8827-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8827-107">Remarks</span></span>  
 <span data-ttu-id="f8827-108">Если эта сборка является системную сборку `GetAppDomain` возвращает значение null.</span><span class="sxs-lookup"><span data-stu-id="f8827-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8827-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f8827-109">Requirements</span></span>  
 <span data-ttu-id="f8827-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8827-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8827-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8827-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8827-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8827-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8827-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8827-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
