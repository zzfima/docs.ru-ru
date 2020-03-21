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
ms.openlocfilehash: adc8ea16f0ab2bf383f8a63c49ba7d61c6bac113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176452"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="afde3-102">Функция CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="afde3-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="afde3-103">Создает объект [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) на основе указанной информации версии.</span><span class="sxs-lookup"><span data-stu-id="afde3-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="afde3-104">Эта функция устарела в рамках .NET 4.</span><span class="sxs-lookup"><span data-stu-id="afde3-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="afde3-105">Вместо этого, чтобы получить интерфейс для общего времени выполнения языка (CLR) 2.0, используйте метод [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) и укажите идентификатор класса CLSID_CLRDebuggingLegacy и идентификатор интерфейса IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="afde3-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="afde3-106">Чтобы получить интерфейс для CLR 4 или позже, позвоните в функцию [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) и укажите идентификатор класса CLSID_CLRDebugging и идентификатор интерфейса IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="afde3-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afde3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="afde3-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afde3-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="afde3-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="afde3-109">(в) Версия `ICorDebug` этого, как ожидается, отладчик.</span><span class="sxs-lookup"><span data-stu-id="afde3-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="afde3-110">Смотрите перечисление [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) для допустимых значений.</span><span class="sxs-lookup"><span data-stu-id="afde3-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="afde3-111">(в) Общая версия выполнения языка, связанная с приложением или процессом для отладки.</span><span class="sxs-lookup"><span data-stu-id="afde3-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="afde3-112">Ознакомиться с информацией о получении этого значения можно посмотреть в методе [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) или [GetRequestedRuntimeVersion.](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)</span><span class="sxs-lookup"><span data-stu-id="afde3-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="afde3-113">(ваут) Место, которое получает указатель на `ICorDebug` объект.</span><span class="sxs-lookup"><span data-stu-id="afde3-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afde3-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="afde3-114">Return Value</span></span>  
 <span data-ttu-id="afde3-115">Этот метод возвращает стандартные коды ошибок COM, определенные в файле WinError.h в дополнение к следующим значениям.</span><span class="sxs-lookup"><span data-stu-id="afde3-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="afde3-116">Код возврата</span><span class="sxs-lookup"><span data-stu-id="afde3-116">Return code</span></span>|<span data-ttu-id="afde3-117">Описание</span><span class="sxs-lookup"><span data-stu-id="afde3-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="afde3-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="afde3-118">S_OK</span></span>|<span data-ttu-id="afde3-119">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="afde3-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="afde3-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="afde3-120">E_INVALIDARG</span></span>|<span data-ttu-id="afde3-121">`szDebuggeeVersion`или `ppCordb` является нулевым, или строка версии неверна.</span><span class="sxs-lookup"><span data-stu-id="afde3-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afde3-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="afde3-122">Remarks</span></span>  
 <span data-ttu-id="afde3-123">Параметр `szDebuggeeVersion` отображает соответствующую версию MSCorDbi.dll.</span><span class="sxs-lookup"><span data-stu-id="afde3-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afde3-124">Требования</span><span class="sxs-lookup"><span data-stu-id="afde3-124">Requirements</span></span>  
 <span data-ttu-id="afde3-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afde3-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afde3-126">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="afde3-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="afde3-127">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="afde3-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="afde3-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afde3-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afde3-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="afde3-129">See also</span></span>

- [<span data-ttu-id="afde3-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="afde3-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
