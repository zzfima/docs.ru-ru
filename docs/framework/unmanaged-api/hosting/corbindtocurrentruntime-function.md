---
title: "Функция CorBindToCurrentRuntime"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type: HeaderDef
f1_keywords: CorBindToCurrentRuntime
helpviewer_keywords: CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0fed8829f8f14833724d1770273ff905d6f5eabf
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="5c631-102">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="5c631-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="5c631-103">Загружает общеязыковой среды выполнения (CLR) в процесс, используя сведения, хранящиеся в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="5c631-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="5c631-104">Формат XML-файла моделируется после стандартного файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="5c631-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="5c631-105">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="5c631-105">For more information about configuration files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="5c631-106">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c631-106">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="5c631-107">В разделе [загрузка общеязыковая среда выполнения в процесс](http://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).</span><span class="sxs-lookup"><span data-stu-id="5c631-107">See [Loading the Common Language Runtime into a Process](http://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c631-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c631-108">Syntax</span></span>  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c631-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c631-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="5c631-110">[in] Имя файла конфигурации приложения, которое указывает версию среды CLR для загрузки.</span><span class="sxs-lookup"><span data-stu-id="5c631-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="5c631-111">Если имя файла не полное, предполагается находиться в том же каталоге, что и исполняемый файл вызова.</span><span class="sxs-lookup"><span data-stu-id="5c631-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="5c631-112">Версия среды выполнения для загрузки описан в атрибуте версии [ \<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) элемента файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5c631-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="5c631-113">Если версия не указана или `<requiredRuntime>` элемент не найден, загружается последняя версия среды CLR, которая установлена на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5c631-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="5c631-114">[in] `CLSID` Компонентного класса, который реализует или [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5c631-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="5c631-115">Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="5c631-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="5c631-116">[in] `IID` Интерфейса, для которого запрашивается.</span><span class="sxs-lookup"><span data-stu-id="5c631-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="5c631-117">Поддерживаемыми значениями являются IID_ICorRuntimeHost и IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="5c631-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="5c631-118">[out] Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5c631-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c631-119">Требования</span><span class="sxs-lookup"><span data-stu-id="5c631-119">Requirements</span></span>  
 <span data-ttu-id="5c631-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c631-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c631-121">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5c631-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c631-122">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c631-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c631-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c631-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c631-124">См. также</span><span class="sxs-lookup"><span data-stu-id="5c631-124">See Also</span></span>  
 [<span data-ttu-id="5c631-125">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="5c631-125">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="5c631-126">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="5c631-126">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="5c631-127">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="5c631-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="5c631-128">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="5c631-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="5c631-129">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="5c631-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="5c631-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="5c631-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
