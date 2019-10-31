---
title: Функция GetCLRIdentityManager
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
ms.openlocfilehash: 3c6def32c63e3557a4de72baf7b1c3e67feb4891
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136531"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="9b2c2-102">Функция GetCLRIdentityManager</span><span class="sxs-lookup"><span data-stu-id="9b2c2-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="9b2c2-103">Возвращает указатель на интерфейс, который позволяет среде CLR управлять удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="9b2c2-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="9b2c2-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9b2c2-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b2c2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b2c2-105">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b2c2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b2c2-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="9b2c2-107">окне `REFIID` (идентификатор интерфейса), указывающий, какой интерфейс следует получить.</span><span class="sxs-lookup"><span data-stu-id="9b2c2-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="9b2c2-108">Это значение должно быть либо IID_ICLRAssemblyIdentityManager, либо IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="9b2c2-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="9b2c2-109">заполняет Указатель на адрес объекта [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) или [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9b2c2-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b2c2-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="9b2c2-110">Remarks</span></span>  
 <span data-ttu-id="9b2c2-111">Вызовите функцию [жетреалпрокаддресс](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) , чтобы получить указатель на функцию `GetCLRIdentityManager`.</span><span class="sxs-lookup"><span data-stu-id="9b2c2-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b2c2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9b2c2-112">Requirements</span></span>  
 <span data-ttu-id="9b2c2-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b2c2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b2c2-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9b2c2-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b2c2-115">**Библиотека:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="9b2c2-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="9b2c2-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b2c2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b2c2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9b2c2-117">See also</span></span>

- [<span data-ttu-id="9b2c2-118">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="9b2c2-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
