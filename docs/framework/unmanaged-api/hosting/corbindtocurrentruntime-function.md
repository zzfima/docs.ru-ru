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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 021f2b7a720c2190d56bdb2b35214c581a7b5f56
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43872144"
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="d6014-102">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="d6014-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="d6014-103">Загружает общеязыковой среды выполнения (CLR) в процесс, используя сведения, хранящиеся в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="d6014-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="d6014-104">Формат XML-файла моделируется стандартного файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="d6014-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="d6014-105">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="d6014-105">For more information about configuration files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="d6014-106">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6014-106">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="d6014-107">См. в разделе [загрузка среда CLR в процесс](https://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).</span><span class="sxs-lookup"><span data-stu-id="d6014-107">See [Loading the Common Language Runtime into a Process](https://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6014-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6014-108">Syntax</span></span>  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6014-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="d6014-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="d6014-110">[in] Имя файла конфигурации приложения, который указывает версию среды CLR для загрузки.</span><span class="sxs-lookup"><span data-stu-id="d6014-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="d6014-111">Если имя файла не указано полное имя, предполагается, что он является в том же каталоге, что и исполняемый файл, вызывающий.</span><span class="sxs-lookup"><span data-stu-id="d6014-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="d6014-112">Версия среды выполнения необходимо загрузить описан в атрибуте версии [ \<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) элемент файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d6014-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="d6014-113">Если версия не указана или если `<requiredRuntime>` элемент не найден, загружается последняя версия среды CLR, которая установлена на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d6014-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="d6014-114">[in] `CLSID` Компонентного класса, реализующий [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d6014-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="d6014-115">Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="d6014-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="d6014-116">[in] `IID` Интерфейса, для которого запрашивается.</span><span class="sxs-lookup"><span data-stu-id="d6014-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="d6014-117">Поддерживаемые значения: IID_ICorRuntimeHost и IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="d6014-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="d6014-118">[out] Возвращаемый указатель интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d6014-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6014-119">Требования</span><span class="sxs-lookup"><span data-stu-id="d6014-119">Requirements</span></span>  
 <span data-ttu-id="d6014-120">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6014-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6014-121">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d6014-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d6014-122">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d6014-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d6014-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6014-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6014-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d6014-124">See Also</span></span>  
 [<span data-ttu-id="d6014-125">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="d6014-125">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="d6014-126">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="d6014-126">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="d6014-127">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="d6014-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="d6014-128">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d6014-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="d6014-129">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d6014-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="d6014-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="d6014-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
