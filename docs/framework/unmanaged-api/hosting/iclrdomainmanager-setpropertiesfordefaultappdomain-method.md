---
title: Метод ICLRDomainManager::SetPropertiesForDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
ms.openlocfilehash: 37919be2d0ebd7d243615bc5845b0781ac13e574
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129317"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="e7745-102">Метод ICLRDomainManager::SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="e7745-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>
<span data-ttu-id="e7745-103">Задает свойства, которые будут использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e7745-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7745-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7745-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7745-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7745-105">Parameters</span></span>  
 `nProperties`  
 <span data-ttu-id="e7745-106">окне Число записей в `pwszPropertyNames` и `pwszPropertyValues`.</span><span class="sxs-lookup"><span data-stu-id="e7745-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="e7745-107">окне Массив имен свойств или значение null, если свойства отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="e7745-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="e7745-108">В настоящее время единственным именем свойства, распознаваемым этим методом, является "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="e7745-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="e7745-109">окне Массив значений свойств или значение null, если свойства отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="e7745-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7745-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e7745-110">Return Value</span></span>  
 <span data-ttu-id="e7745-111">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="e7745-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e7745-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e7745-112">HRESULT</span></span>|<span data-ttu-id="e7745-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e7745-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7745-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7745-114">S_OK</span></span>|<span data-ttu-id="e7745-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="e7745-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="e7745-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="e7745-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="e7745-117">`pwszPropertyNames` содержит имя свойства, которое не распознается этим методом.</span><span class="sxs-lookup"><span data-stu-id="e7745-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7745-118">Заметки</span><span class="sxs-lookup"><span data-stu-id="e7745-118">Remarks</span></span>  
 <span data-ttu-id="e7745-119">Значение свойства для "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" — это список сборок, имеющих атрибут Conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) с флагом <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType>, которые должны быть видимыми для частично доверенных вызывающих объектов в домене приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e7745-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7745-120">Требования</span><span class="sxs-lookup"><span data-stu-id="e7745-120">Requirements</span></span>  
 <span data-ttu-id="e7745-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7745-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7745-122">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="e7745-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e7745-123">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e7745-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7745-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7745-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7745-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e7745-125">See also</span></span>

- [<span data-ttu-id="e7745-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="e7745-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="e7745-127">Интерфейс ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="e7745-127">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
