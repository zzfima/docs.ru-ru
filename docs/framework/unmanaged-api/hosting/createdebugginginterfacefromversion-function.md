---
title: Функция CreateDebuggingInterfaceFromVersion
ms.date: 03/30/2017
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60d1c49e8762d00e3e154c598c2542c4a76b9b28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107501"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="621b3-102">Функция CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="621b3-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="621b3-103">Создает [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) объекта на основе указанной версии данных.</span><span class="sxs-lookup"><span data-stu-id="621b3-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="621b3-104">Эта функция является устаревшей в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="621b3-104">This function is obsolete in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="621b3-105">Вместо этого, чтобы получить интерфейс для общеязыковой среды выполнения (CLR) 2.0, используйте [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) метод и укажите идентификатор класса CLSID_CLRDebuggingLegacy и IID_ICorDebug идентификатор интерфейса.</span><span class="sxs-lookup"><span data-stu-id="621b3-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="621b3-106">Чтобы получить интерфейс для CLR 4 или более поздней версии, вызовите [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) функцию и укажите идентификатор класса CLSID_CLRDebugging и IID_ICLRDebugging идентификатор интерфейса.</span><span class="sxs-lookup"><span data-stu-id="621b3-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="621b3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="621b3-107">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="621b3-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="621b3-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="621b3-109">[in] Версия `ICorDebug` ведь отладчиком.</span><span class="sxs-lookup"><span data-stu-id="621b3-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="621b3-110">См. в разделе [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) перечисления для допустимых значений.</span><span class="sxs-lookup"><span data-stu-id="621b3-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="621b3-111">[in] Распространенные версию среды CLR, связанный с приложением или процесс для отладки.</span><span class="sxs-lookup"><span data-stu-id="621b3-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="621b3-112">См. в разделе [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) или [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) сведения о получении этого значения.</span><span class="sxs-lookup"><span data-stu-id="621b3-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="621b3-113">[out] Получает указатель на расположение `ICorDebug` объекта.</span><span class="sxs-lookup"><span data-stu-id="621b3-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="621b3-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="621b3-114">Return Value</span></span>  
 <span data-ttu-id="621b3-115">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, а также следующие значения.</span><span class="sxs-lookup"><span data-stu-id="621b3-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="621b3-116">Код возврата</span><span class="sxs-lookup"><span data-stu-id="621b3-116">Return code</span></span>|<span data-ttu-id="621b3-117">Описание</span><span class="sxs-lookup"><span data-stu-id="621b3-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="621b3-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="621b3-118">S_OK</span></span>|<span data-ttu-id="621b3-119">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="621b3-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="621b3-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="621b3-120">E_INVALIDARG</span></span>|<span data-ttu-id="621b3-121">`szDebuggeeVersion` или `ppCordb` имеет значение null, или версии Неверная строка.</span><span class="sxs-lookup"><span data-stu-id="621b3-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="621b3-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="621b3-122">Remarks</span></span>  
 <span data-ttu-id="621b3-123">`szDebuggeeVersion` Параметр сопоставляется с соответствующей версией библиотеки MSCorDbi.dll.</span><span class="sxs-lookup"><span data-stu-id="621b3-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="621b3-124">Требования</span><span class="sxs-lookup"><span data-stu-id="621b3-124">Requirements</span></span>  
 <span data-ttu-id="621b3-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="621b3-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="621b3-126">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="621b3-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="621b3-127">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="621b3-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="621b3-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="621b3-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="621b3-129">См. также</span><span class="sxs-lookup"><span data-stu-id="621b3-129">See also</span></span>

- [<span data-ttu-id="621b3-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="621b3-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
