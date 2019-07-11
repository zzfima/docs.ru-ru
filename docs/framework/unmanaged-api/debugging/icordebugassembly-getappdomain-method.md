---
title: Метод ICorDebugAssembly::GetAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetAppDomain
helpviewer_keywords:
- ICorDebugAssembly::GetAppDomain method [.NET Framework debugging]
- GetAppDomain method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 14e18510-23ac-4cba-9f96-c86147a2df9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4fced656168952c1064de213405147baf7856b2c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737354"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="0717e-102">Метод ICorDebugAssembly::GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="0717e-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="0717e-103">Получает указатель интерфейса на домен приложения, который содержит это `ICorDebugAssembly` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0717e-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0717e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0717e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0717e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0717e-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="0717e-106">[out] Указатель на адрес ICorDebugAppDomain-интерфейс, который представляет домен приложения.</span><span class="sxs-lookup"><span data-stu-id="0717e-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0717e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="0717e-107">Remarks</span></span>  
 <span data-ttu-id="0717e-108">Если эта сборка является сборкой системы, `GetAppDomain` возвращает значение null.</span><span class="sxs-lookup"><span data-stu-id="0717e-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0717e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0717e-109">Requirements</span></span>  
 <span data-ttu-id="0717e-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0717e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0717e-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0717e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0717e-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0717e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0717e-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0717e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
