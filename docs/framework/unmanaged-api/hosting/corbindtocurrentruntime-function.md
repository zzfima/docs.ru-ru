---
title: Функция CorBindToCurrentRuntime
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
ms.openlocfilehash: 77a0a8f58c11673a1958d837b4c3a21a05754c94
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138321"
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="7437d-102">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="7437d-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="7437d-103">Загружает среду CLR в процесс с использованием сведений о версии, хранящихся в XML-файле.</span><span class="sxs-lookup"><span data-stu-id="7437d-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="7437d-104">Формат XML-файла моделируется после стандартного файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="7437d-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="7437d-105">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="7437d-105">For more information about configuration files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="7437d-106">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="7437d-106">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="7437d-107">См. раздел [Загрузка среды CLR в процесс](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="7437d-107">See [Loading the Common Language Runtime into a Process](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7437d-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7437d-108">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7437d-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="7437d-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="7437d-110">окне Имя файла конфигурации приложения, указывающего версию среды CLR для загрузки.</span><span class="sxs-lookup"><span data-stu-id="7437d-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="7437d-111">Если имя файла не указано полностью, предполагается, что он находится в том же каталоге, что и исполняемый объект, вызывающий вызов.</span><span class="sxs-lookup"><span data-stu-id="7437d-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="7437d-112">Версия загружаемой среды выполнения описывается атрибутом Version в элементе [\<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7437d-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="7437d-113">Если версия не указана или не удается найти элемент `<requiredRuntime>`, загружается последняя версия среды CLR, установленная на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7437d-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="7437d-114">окне `CLSID` компонентного класса, реализующего интерфейс [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7437d-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="7437d-115">Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="7437d-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="7437d-116">окне `IID` запрашиваемого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7437d-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="7437d-117">Поддерживаемые значения: IID_ICorRuntimeHost или IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="7437d-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="7437d-118">заполняет Возвращаемый указатель интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7437d-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7437d-119">Требования</span><span class="sxs-lookup"><span data-stu-id="7437d-119">Requirements</span></span>  
 <span data-ttu-id="7437d-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7437d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7437d-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7437d-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7437d-122">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7437d-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7437d-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7437d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7437d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="7437d-124">See also</span></span>

- [<span data-ttu-id="7437d-125">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="7437d-125">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="7437d-126">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="7437d-126">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="7437d-127">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="7437d-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="7437d-128">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="7437d-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="7437d-129">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="7437d-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="7437d-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="7437d-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
