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
ms.openlocfilehash: 9a02a899fd6fbffd04ef25913adb6a65ade27177
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755662"
---
# <a name="cordllmain-function"></a><span data-ttu-id="86a07-102">\_Функция CorDllMain</span><span class="sxs-lookup"><span data-stu-id="86a07-102">\_CorDllMain Function</span></span>

<span data-ttu-id="86a07-103">Инициализирует общеязыковой среды выполнения (CLR), размещает управляемую точку входа в заголовке среды CLR сборки DLL и начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="86a07-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86a07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86a07-104">Syntax</span></span>  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86a07-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86a07-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="86a07-106">[in] Дескриптор экземпляра загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="86a07-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="86a07-107">[in] Указывает, почему вызывается функция точки входа библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="86a07-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="86a07-108">Этот параметр может принимать одно из следующих значений: Библиотеки DLL\_PROCESS_ATTACH, DLL\_ПОТОКОВ\_ATTACH, DLL\_ПОТОКОВ\_ATTACH или DLL\_процесс\_ОТСОЕДИНЕНИЯ.</span><span class="sxs-lookup"><span data-stu-id="86a07-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="86a07-109">Описание этих значений, см. в разделе `DllMain` документации пакета Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="86a07-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="86a07-110">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="86a07-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86a07-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="86a07-111">Return Value</span></span>  
 <span data-ttu-id="86a07-112">Этот метод возвращает `true` для достижения успеха и `false` при возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="86a07-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86a07-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="86a07-113">Remarks</span></span>  
 <span data-ttu-id="86a07-114">Эта функция вызывается загрузчиком операционной системы для DLL-сборки.</span><span class="sxs-lookup"><span data-stu-id="86a07-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="86a07-115">Исполняемые сборки, загрузчик вызывает [ \_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) вместо этого функцию.</span><span class="sxs-lookup"><span data-stu-id="86a07-115">For executable assemblies, the loader calls the [\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="86a07-116">Загрузчик операционной системы вызывает этот метод независимо от точки входа, указанной в файле DLL.</span><span class="sxs-lookup"><span data-stu-id="86a07-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="86a07-117">`_CorDllMain` Функция вызывается загрузчиком операционной системы.</span><span class="sxs-lookup"><span data-stu-id="86a07-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="86a07-118">Дополнительные сведения см. в разделе "Примечания" в [ \_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="86a07-118">For additional information, see the Remarks section in the [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86a07-119">Требования</span><span class="sxs-lookup"><span data-stu-id="86a07-119">Requirements</span></span>  

 <span data-ttu-id="86a07-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86a07-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86a07-121">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="86a07-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86a07-122">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="86a07-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86a07-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86a07-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86a07-124">См. также</span><span class="sxs-lookup"><span data-stu-id="86a07-124">See also</span></span>

- [<span data-ttu-id="86a07-125">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="86a07-125">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
