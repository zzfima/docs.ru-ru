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
ms.openlocfilehash: 1b51b924652019cf05401e1972797c18e74b82d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="db127-102">Функция CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="db127-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="db127-103">Создает [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) объекта на основе указанной версии данных.</span><span class="sxs-lookup"><span data-stu-id="db127-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="db127-104">Эта функция устарела в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db127-104">This function is obsolete in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="db127-105">Для обеспечения интерфейса для общеязыковой среды выполнения (CLR) 2.0, используйте [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) метод и задайте идентификатор класса CLSID_CLRDebuggingLegacy идентификатор интерфейса IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="db127-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="db127-106">Для получения интерфейса для CLR 4 или более поздней версии, вызовите [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) и задайте идентификатор класса CLSID_CLRDebugging и IID_ICLRDebugging идентификатор интерфейса.</span><span class="sxs-lookup"><span data-stu-id="db127-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db127-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db127-107">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db127-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="db127-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="db127-109">[in] Версия `ICorDebug` , ожидается отладчиком.</span><span class="sxs-lookup"><span data-stu-id="db127-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="db127-110">В разделе [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) перечисления для допустимых значений.</span><span class="sxs-lookup"><span data-stu-id="db127-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="db127-111">[in] Общие версию среды CLR, связанный с приложением или процесс для отладки.</span><span class="sxs-lookup"><span data-stu-id="db127-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="db127-112">В разделе [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) или [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) метод сведения о получении этого значения.</span><span class="sxs-lookup"><span data-stu-id="db127-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="db127-113">[out] В расположение, которое получает указатель на `ICorDebug` объект.</span><span class="sxs-lookup"><span data-stu-id="db127-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db127-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="db127-114">Return Value</span></span>  
 <span data-ttu-id="db127-115">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, кроме следующих значений.</span><span class="sxs-lookup"><span data-stu-id="db127-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="db127-116">Код возврата</span><span class="sxs-lookup"><span data-stu-id="db127-116">Return code</span></span>|<span data-ttu-id="db127-117">Описание</span><span class="sxs-lookup"><span data-stu-id="db127-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="db127-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="db127-118">S_OK</span></span>|<span data-ttu-id="db127-119">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="db127-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="db127-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="db127-120">E_INVALIDARG</span></span>|<span data-ttu-id="db127-121">`szDebuggeeVersion` или `ppCordb` имеет значение null или версия Неверная строка.</span><span class="sxs-lookup"><span data-stu-id="db127-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db127-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="db127-122">Remarks</span></span>  
 <span data-ttu-id="db127-123">`szDebuggeeVersion` Параметр сопоставляется соответствующую версию библиотеки MSCorDbi.dll.</span><span class="sxs-lookup"><span data-stu-id="db127-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db127-124">Требования</span><span class="sxs-lookup"><span data-stu-id="db127-124">Requirements</span></span>  
 <span data-ttu-id="db127-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db127-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db127-126">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="db127-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db127-127">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="db127-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db127-128">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db127-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db127-129">См. также</span><span class="sxs-lookup"><span data-stu-id="db127-129">See Also</span></span>  
 [<span data-ttu-id="db127-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="db127-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
