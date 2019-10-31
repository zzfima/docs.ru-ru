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
ms.openlocfilehash: e23dfb86c2129a02a0ca95de8c89d8294e97ad81
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136841"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="c075c-102">Функция CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="c075c-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="c075c-103">Создает объект [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) на основе указанных сведений о версии.</span><span class="sxs-lookup"><span data-stu-id="c075c-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="c075c-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c075c-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="c075c-105">Вместо этого для получения интерфейса для среды CLR 2,0 используйте метод [ICLRRuntimeInfo::](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) coclass и укажите идентификатор класса CLSID_CLRDebuggingLegacy и идентификатор интерфейса IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="c075c-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="c075c-106">Чтобы получить интерфейс для CLR 4 или более поздней версии, вызовите функцию [клркреатеинстанце](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) и укажите идентификатор класса CLSID_CLRDebugging и идентификатор интерфейса IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="c075c-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c075c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c075c-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c075c-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="c075c-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="c075c-109">окне Версия `ICorDebug`, ожидаемая отладчиком.</span><span class="sxs-lookup"><span data-stu-id="c075c-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="c075c-110">Допустимые значения см. в описании перечисления [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="c075c-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="c075c-111">окне Версия среды CLR, связанная с приложением или процессом для отладки.</span><span class="sxs-lookup"><span data-stu-id="c075c-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="c075c-112">Сведения о получении этого значения см. в описании метода [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) или [жетрекуестедрунтимеверсион](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="c075c-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="c075c-113">заполняет Расположение, которое получает указатель на объект `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="c075c-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c075c-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c075c-114">Return Value</span></span>  
 <span data-ttu-id="c075c-115">Этот метод возвращает стандартные коды ошибок COM, определенные в файле WinError. h, а также следующие значения.</span><span class="sxs-lookup"><span data-stu-id="c075c-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="c075c-116">Код возврата</span><span class="sxs-lookup"><span data-stu-id="c075c-116">Return code</span></span>|<span data-ttu-id="c075c-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c075c-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c075c-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="c075c-118">S_OK</span></span>|<span data-ttu-id="c075c-119">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="c075c-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="c075c-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c075c-120">E_INVALIDARG</span></span>|<span data-ttu-id="c075c-121">`szDebuggeeVersion` или `ppCordb` имеет значение null или строка версии неверна.</span><span class="sxs-lookup"><span data-stu-id="c075c-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c075c-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="c075c-122">Remarks</span></span>  
 <span data-ttu-id="c075c-123">Параметр `szDebuggeeVersion` сопоставляется с соответствующей версией MSCorDbi. dll.</span><span class="sxs-lookup"><span data-stu-id="c075c-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c075c-124">Требования</span><span class="sxs-lookup"><span data-stu-id="c075c-124">Requirements</span></span>  
 <span data-ttu-id="c075c-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c075c-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c075c-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c075c-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c075c-127">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c075c-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c075c-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c075c-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c075c-129">См. также</span><span class="sxs-lookup"><span data-stu-id="c075c-129">See also</span></span>

- [<span data-ttu-id="c075c-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="c075c-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
