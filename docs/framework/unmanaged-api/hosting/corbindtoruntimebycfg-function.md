---
title: Функция CorBindToRuntimeByCfg
ms.date: 03/30/2017
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
ms.openlocfilehash: 4fbc6e7ea531f65a6b1cd0ec93f4847ab8e4fe83
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178246"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="8d727-102">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="8d727-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="8d727-103">Загружает время выполнения общего языка (CLR) в процесс, используя информацию о версии, которая читается из файла XML.</span><span class="sxs-lookup"><span data-stu-id="8d727-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="8d727-104">Эта функция была унесена в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="8d727-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d727-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d727-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d727-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8d727-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="8d727-107">(в) Указатель на `IStream` объект, который читает файл XML.</span><span class="sxs-lookup"><span data-stu-id="8d727-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="8d727-108">[in] Зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="8d727-108">[in] Reserved for future use.</span></span> <span data-ttu-id="8d727-109">Используйте 0 (ноль) в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="8d727-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="8d727-110">(в) Значение [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) перечисления, которое определяет поведение стартапа CLR.</span><span class="sxs-lookup"><span data-stu-id="8d727-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="8d727-111">(в) Кокласс, `CLSID` который реализует либо [iCorRuntimeHost,](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) либо интерфейс [ICLRRuntimeHost.](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)</span><span class="sxs-lookup"><span data-stu-id="8d727-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="8d727-112">Поддерживаемые значения являются CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="8d727-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="8d727-113">(в) Либо `IID` или `ICorRuntimeHost` `ICLRRuntimeHost` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8d727-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="8d727-114">Поддерживаемые значения IID_ICorRuntimeHost или IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="8d727-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="8d727-115">(ваут) Указатель на адрес возвращенного интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8d727-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d727-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="8d727-116">Remarks</span></span>  
 <span data-ttu-id="8d727-117">Формат файла XML моделируется после стандартного файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="8d727-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="8d727-118">Для получения дополнительной информации о файлах XML [см.](../../../../docs/framework/configure-apps/file-schema/index.md)</span><span class="sxs-lookup"><span data-stu-id="8d727-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d727-119">Требования</span><span class="sxs-lookup"><span data-stu-id="8d727-119">Requirements</span></span>  
 <span data-ttu-id="8d727-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d727-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d727-121">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8d727-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d727-122">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d727-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d727-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d727-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d727-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8d727-124">See also</span></span>

- [<span data-ttu-id="8d727-125">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="8d727-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="8d727-126">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="8d727-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="8d727-127">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="8d727-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="8d727-128">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="8d727-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="8d727-129">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="8d727-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="8d727-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="8d727-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
