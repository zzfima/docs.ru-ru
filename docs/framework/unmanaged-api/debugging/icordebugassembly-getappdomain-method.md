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
ms.openlocfilehash: 53042e722809a6574396648529c677d749154716
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132727"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="a9f8a-102">Метод ICorDebugAssembly::GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="a9f8a-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="a9f8a-103">Возвращает указатель интерфейса на домен приложения, содержащий данный `ICorDebugAssembly` экземпляр.</span><span class="sxs-lookup"><span data-stu-id="a9f8a-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9f8a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9f8a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9f8a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a9f8a-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="a9f8a-106">заполняет Указатель на адрес интерфейса ICorDebugAppDomain, который представляет домен приложения.</span><span class="sxs-lookup"><span data-stu-id="a9f8a-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9f8a-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="a9f8a-107">Remarks</span></span>  
 <span data-ttu-id="a9f8a-108">Если эта сборка является системной, `GetAppDomain` возвращает значение null.</span><span class="sxs-lookup"><span data-stu-id="a9f8a-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9f8a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a9f8a-109">Requirements</span></span>  
 <span data-ttu-id="a9f8a-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9f8a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9f8a-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9f8a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9f8a-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9f8a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9f8a-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9f8a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
