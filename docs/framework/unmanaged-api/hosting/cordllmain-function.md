---
title: Функция _CorDllMain
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3c529e77cad16f0bde12e34491829b58add17aa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500395"
---
# <a name="cordllmain-function"></a><span data-ttu-id="f9a3d-102">Функция _CorDllMain</span><span class="sxs-lookup"><span data-stu-id="f9a3d-102">_CorDllMain Function</span></span>
<span data-ttu-id="f9a3d-103">Инициализирует общеязыковой среды выполнения (CLR), размещает управляемую точку входа в заголовке среды CLR сборки DLL и начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="f9a3d-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9a3d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9a3d-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9a3d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9a3d-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="f9a3d-106">[in] Дескриптор экземпляра загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="f9a3d-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="f9a3d-107">[in] Указывает, почему вызывается функция точки входа библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="f9a3d-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="f9a3d-108">Этот параметр может принимать одно из следующих значений: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH или DLL_PROCESS_DETACH.</span><span class="sxs-lookup"><span data-stu-id="f9a3d-108">This parameter can be one of the following values: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH, or DLL_PROCESS_DETACH.</span></span> <span data-ttu-id="f9a3d-109">Описание этих значений, см. в разделе `DllMain` документации пакета Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="f9a3d-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="f9a3d-110">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="f9a3d-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9a3d-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f9a3d-111">Return Value</span></span>  
 <span data-ttu-id="f9a3d-112">Этот метод возвращает `true` для достижения успеха и `false` при возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="f9a3d-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9a3d-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="f9a3d-113">Remarks</span></span>  
 <span data-ttu-id="f9a3d-114">Эта функция вызывается загрузчиком операционной системы для DLL-сборки.</span><span class="sxs-lookup"><span data-stu-id="f9a3d-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="f9a3d-115">Исполняемые сборки, загрузчик вызывает [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) вместо этого функцию.</span><span class="sxs-lookup"><span data-stu-id="f9a3d-115">For executable assemblies, the loader calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="f9a3d-116">Загрузчик операционной системы вызывает этот метод независимо от точки входа, указанной в файле DLL.</span><span class="sxs-lookup"><span data-stu-id="f9a3d-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="f9a3d-117">`_CorDllMain` Функция вызывается загрузчиком операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f9a3d-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="f9a3d-118">Дополнительные сведения см. в разделе "Примечания" в [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="f9a3d-118">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9a3d-119">Требования</span><span class="sxs-lookup"><span data-stu-id="f9a3d-119">Requirements</span></span>  
 <span data-ttu-id="f9a3d-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9a3d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9a3d-121">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f9a3d-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f9a3d-122">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9a3d-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f9a3d-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9a3d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a3d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f9a3d-124">See also</span></span>
- [<span data-ttu-id="f9a3d-125">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="f9a3d-125">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
