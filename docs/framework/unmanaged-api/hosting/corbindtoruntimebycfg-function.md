---
title: "Функция CorBindToRuntimeByCfg"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2dccd777ef20f68d091cfdd7939c57a1f8d42ad5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="367c7-102">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="367c7-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="367c7-103">Загружает общеязыковой среды выполнения (CLR) в процесс, используя сведения о версии, считываемые из файла XML.</span><span class="sxs-lookup"><span data-stu-id="367c7-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="367c7-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="367c7-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="367c7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="367c7-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,   
    [out] LPVOID FAR*  ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="367c7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="367c7-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="367c7-107">[in] Указатель на `IStream` объект, который считывает XML-файл.</span><span class="sxs-lookup"><span data-stu-id="367c7-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="367c7-108">[in] Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="367c7-108">[in] Reserved for future use.</span></span> <span data-ttu-id="367c7-109">Использовать в качестве значения 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="367c7-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="367c7-110">[in] Значение [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) перечисления, определяющее режим запуска среды CLR.</span><span class="sxs-lookup"><span data-stu-id="367c7-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="367c7-111">[in] `CLSID` Компонентного класса, который реализует или [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="367c7-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="367c7-112">Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="367c7-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="367c7-113">[in] `IID` Любого `ICorRuntimeHost` или `ICLRRuntimeHost` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="367c7-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="367c7-114">Поддерживаемыми значениями являются IID_ICorRuntimeHost и IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="367c7-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="367c7-115">[out] Указатель на адрес возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="367c7-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="367c7-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="367c7-116">Remarks</span></span>  
 <span data-ttu-id="367c7-117">Формат XML-файла моделируется после стандартного файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="367c7-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="367c7-118">Дополнительные сведения о XML-файлов см. в разделе [схема файла конфигурации](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="367c7-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="367c7-119">Требования</span><span class="sxs-lookup"><span data-stu-id="367c7-119">Requirements</span></span>  
 <span data-ttu-id="367c7-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="367c7-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="367c7-121">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="367c7-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="367c7-122">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="367c7-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="367c7-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="367c7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="367c7-124">См. также</span><span class="sxs-lookup"><span data-stu-id="367c7-124">See Also</span></span>  
 [<span data-ttu-id="367c7-125">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="367c7-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="367c7-126">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="367c7-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="367c7-127">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="367c7-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="367c7-128">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="367c7-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="367c7-129">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="367c7-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="367c7-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="367c7-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
