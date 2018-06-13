---
title: Метод IHostMemoryManager::VirtualQuery
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualQuery
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68a9d6ad7470ffaf1143a4a8e3134f20edb9e3c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439223"
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="32f64-102">Метод IHostMemoryManager::VirtualQuery</span><span class="sxs-lookup"><span data-stu-id="32f64-102">IHostMemoryManager::VirtualQuery Method</span></span>
<span data-ttu-id="32f64-103">Служит в качестве логической программой-оболочкой для соответствующей функции Win32.</span><span class="sxs-lookup"><span data-stu-id="32f64-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="32f64-104">Реализация Win32 `VirtualQuery` извлекает сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="32f64-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32f64-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32f64-105">Syntax</span></span>  
  
```  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32f64-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="32f64-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="32f64-107">[in] Указатель на адрес в виртуальной памяти, должны запрашиваться.</span><span class="sxs-lookup"><span data-stu-id="32f64-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="32f64-108">[out] Указатель на структуру, содержащую сведения о указанную область памяти.</span><span class="sxs-lookup"><span data-stu-id="32f64-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="32f64-109">[in] Размер в байтах буфера, `lpBuffer` указывает.</span><span class="sxs-lookup"><span data-stu-id="32f64-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="32f64-110">[out] Указатель на число байт, возвращенных в буфере сведения.</span><span class="sxs-lookup"><span data-stu-id="32f64-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32f64-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="32f64-111">Return Value</span></span>  
  
|<span data-ttu-id="32f64-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32f64-112">HRESULT</span></span>|<span data-ttu-id="32f64-113">Описание</span><span class="sxs-lookup"><span data-stu-id="32f64-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32f64-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="32f64-114">S_OK</span></span>|<span data-ttu-id="32f64-115">`VirtualQuery` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="32f64-115">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="32f64-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="32f64-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="32f64-117">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="32f64-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="32f64-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="32f64-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="32f64-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="32f64-119">The call timed out.</span></span>|  
|<span data-ttu-id="32f64-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="32f64-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="32f64-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="32f64-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="32f64-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="32f64-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="32f64-123">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="32f64-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="32f64-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="32f64-124">E_FAIL</span></span>|<span data-ttu-id="32f64-125">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="32f64-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="32f64-126">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="32f64-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="32f64-127">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="32f64-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32f64-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="32f64-128">Remarks</span></span>  
 <span data-ttu-id="32f64-129">`VirtualQuery` Предоставляет сведения о диапазоне страниц в виртуальном адресном пространстве вызывающего процесса.</span><span class="sxs-lookup"><span data-stu-id="32f64-129">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="32f64-130">Эта реализация задает значение `pResult` параметр для число байтов, возвращаемых в буфере сведения, а также возвращает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="32f64-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="32f64-131">В Win32 `VirtualQuery` функции, возвращаемое значение равно размеру буфера.</span><span class="sxs-lookup"><span data-stu-id="32f64-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="32f64-132">Дополнительные сведения см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="32f64-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="32f64-133">Реализация операционной системы `VirtualQuery` не приводит к взаимоблокировке и может работать до завершения при случайной приостановки потоков в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="32f64-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="32f64-134">Будьте осторожны значительные реализацию версии данного метода.</span><span class="sxs-lookup"><span data-stu-id="32f64-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32f64-135">Требования</span><span class="sxs-lookup"><span data-stu-id="32f64-135">Requirements</span></span>  
 <span data-ttu-id="32f64-136">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32f64-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32f64-137">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="32f64-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32f64-138">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="32f64-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32f64-139">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32f64-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32f64-140">См. также</span><span class="sxs-lookup"><span data-stu-id="32f64-140">See Also</span></span>  
 [<span data-ttu-id="32f64-141">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="32f64-141">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
