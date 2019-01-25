---
title: Метод ICorRuntimeHost::NextDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f8e9c91ddddd0e0b14c79bef86c7665ff4e3dcc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723325"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="bad79-102">Метод ICorRuntimeHost::NextDomain</span><span class="sxs-lookup"><span data-stu-id="bad79-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="bad79-103">Получает указатель интерфейса на следующий домен в перечислении.</span><span class="sxs-lookup"><span data-stu-id="bad79-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bad79-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bad79-104">Syntax</span></span>  
  
```  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bad79-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bad79-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="bad79-106">[in] Перечислитель, который был получен путем вызова [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span><span class="sxs-lookup"><span data-stu-id="bad79-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="bad79-107">[out] Указатель интерфейса на <xref:System._AppDomain?displayProperty=nameWithType> тип, представляющий следующий домен в перечисление, или значение null, если несколько доменов не существует.</span><span class="sxs-lookup"><span data-stu-id="bad79-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bad79-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bad79-108">Return Value</span></span>  
  
|<span data-ttu-id="bad79-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bad79-109">HRESULT</span></span>|<span data-ttu-id="bad79-110">Описание</span><span class="sxs-lookup"><span data-stu-id="bad79-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bad79-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bad79-111">S_OK</span></span>|<span data-ttu-id="bad79-112">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="bad79-112">The operation was successful.</span></span>|  
|<span data-ttu-id="bad79-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="bad79-113">S_FALSE</span></span>|<span data-ttu-id="bad79-114">Не удалось завершить операцию, или нет несколько доменов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="bad79-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="bad79-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bad79-115">E_FAIL</span></span>|<span data-ttu-id="bad79-116">Произошла неизвестная, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="bad79-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="bad79-117">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="bad79-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="bad79-118">Последующие вызовы для любого API хостинга, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bad79-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bad79-119">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bad79-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bad79-120">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="bad79-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bad79-121">Требования</span><span class="sxs-lookup"><span data-stu-id="bad79-121">Requirements</span></span>  
 <span data-ttu-id="bad79-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bad79-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bad79-123">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bad79-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bad79-124">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bad79-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bad79-125">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="bad79-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad79-126">См. также</span><span class="sxs-lookup"><span data-stu-id="bad79-126">See also</span></span>
- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="bad79-127">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="bad79-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
