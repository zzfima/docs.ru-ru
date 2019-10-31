---
title: Метод ICorRuntimeHost::CurrentDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CurrentDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CurrentDomain
helpviewer_keywords:
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
- CurrentDomain method [.NET Framework hosting]
ms.assetid: dd2afb38-675b-4c3c-a9f3-8ab3b133eb02
topic_type:
- apiref
ms.openlocfilehash: f2249d10159b1ff0be7ead0783efb8a2742d26b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139607"
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="0b2dc-102">Метод ICorRuntimeHost::CurrentDomain</span><span class="sxs-lookup"><span data-stu-id="0b2dc-102">ICorRuntimeHost::CurrentDomain Method</span></span>
<span data-ttu-id="0b2dc-103">Возвращает указатель интерфейса типа <xref:System.AppDomain?displayProperty=nameWithType>, представляющий домен, загруженный в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b2dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b2dc-104">Syntax</span></span>  
  
```cpp  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b2dc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b2dc-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0b2dc-106">заполняет Указатель типа <xref:System.AppDomain?displayProperty=nameWithType>, представляющий текущий домен приложения потока.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="0b2dc-107">Этот указатель типизирован `IUnknown`, поэтому вызывающие объекты должны обычно вызывать `QueryInterface` для получения указателя типа <xref:System._AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b2dc-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0b2dc-108">Return Value</span></span>  
  
|<span data-ttu-id="0b2dc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b2dc-109">HRESULT</span></span>|<span data-ttu-id="0b2dc-110">Описание</span><span class="sxs-lookup"><span data-stu-id="0b2dc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b2dc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b2dc-111">S_OK</span></span>|<span data-ttu-id="0b2dc-112">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-112">The operation was successful.</span></span>|  
|<span data-ttu-id="0b2dc-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0b2dc-113">S_FALSE</span></span>|<span data-ttu-id="0b2dc-114">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="0b2dc-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0b2dc-115">E_FAIL</span></span>|<span data-ttu-id="0b2dc-116">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="0b2dc-117">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="0b2dc-118">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0b2dc-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0b2dc-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0b2dc-120">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0b2dc-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b2dc-121">Требования</span><span class="sxs-lookup"><span data-stu-id="0b2dc-121">Requirements</span></span>  
 <span data-ttu-id="0b2dc-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b2dc-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b2dc-123">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0b2dc-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b2dc-124">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0b2dc-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b2dc-125">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="0b2dc-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b2dc-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0b2dc-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="0b2dc-127">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0b2dc-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
