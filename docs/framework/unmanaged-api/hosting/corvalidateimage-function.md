---
title: "Функция _CorValidateImage"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorValidateImage
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorValidateImage
helpviewer_keywords: _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e2396219a5e4bfd95a9dc7134e2e603ed7a15a3d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corvalidateimage-function"></a><span data-ttu-id="5a48e-102">Функция _CorValidateImage</span><span class="sxs-lookup"><span data-stu-id="5a48e-102">_CorValidateImage Function</span></span>
<span data-ttu-id="5a48e-103">Проверяет образы управляемого модуля и уведомляет загрузчик операционной системы после их загрузки.</span><span class="sxs-lookup"><span data-stu-id="5a48e-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a48e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a48e-104">Syntax</span></span>  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a48e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a48e-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="5a48e-106">[in] Указатель начальной позиции образа для проверки, как управляемый код.</span><span class="sxs-lookup"><span data-stu-id="5a48e-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="5a48e-107">Изображение уже должны быть загружены в память.</span><span class="sxs-lookup"><span data-stu-id="5a48e-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="5a48e-108">[in] Имя файла изображения.</span><span class="sxs-lookup"><span data-stu-id="5a48e-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a48e-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5a48e-109">Return Value</span></span>  
 <span data-ttu-id="5a48e-110">Эта функция возвращает стандартные значения `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, и `E_FAIL`, а также следующие значения.</span><span class="sxs-lookup"><span data-stu-id="5a48e-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="5a48e-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5a48e-111">Return value</span></span>|<span data-ttu-id="5a48e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5a48e-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="5a48e-113">Недопустимый образ.</span><span class="sxs-lookup"><span data-stu-id="5a48e-113">The image is invalid.</span></span> <span data-ttu-id="5a48e-114">Это значение имеет HRESULT 0xC000007BL.</span><span class="sxs-lookup"><span data-stu-id="5a48e-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="5a48e-115">Образ является допустимым.</span><span class="sxs-lookup"><span data-stu-id="5a48e-115">The image is valid.</span></span> <span data-ttu-id="5a48e-116">Это значение имеет HRESULT 0x00000000L.</span><span class="sxs-lookup"><span data-stu-id="5a48e-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a48e-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="5a48e-117">Remarks</span></span>  
 <span data-ttu-id="5a48e-118">В Windows XP и более поздних версиях загрузчик операционной системы выполняет поиск управляемых модулей путем анализа бит каталога дескриптора модели COM в заголовке общего формата (COFF) объекта файла.</span><span class="sxs-lookup"><span data-stu-id="5a48e-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="5a48e-119">Установленный бит обозначает управляемый модуль.</span><span class="sxs-lookup"><span data-stu-id="5a48e-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="5a48e-120">При обнаружении управляемый модуль, он загружает MsCorEE.dll и вызывает метод `_CorValidateImage`, который выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5a48e-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
-   <span data-ttu-id="5a48e-121">Подтверждает, что образ является допустимым управляемым модулем.</span><span class="sxs-lookup"><span data-stu-id="5a48e-121">Confirms that the image is a valid managed module.</span></span>  
  
-   <span data-ttu-id="5a48e-122">Заменяет точку входа в образе на точку входа в общеязыковой среде выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="5a48e-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
-   <span data-ttu-id="5a48e-123">Для 64-разрядных версиях Windows изменяет образ, находящийся в памяти, путем преобразования его из формата PE32 в формат PE32 +.</span><span class="sxs-lookup"><span data-stu-id="5a48e-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
-   <span data-ttu-id="5a48e-124">Возврат загрузчик при загрузке образов управляемого модуля.</span><span class="sxs-lookup"><span data-stu-id="5a48e-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="5a48e-125">Для исполняемых образов загрузчик операционной системы затем вызывает [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) функции, независимо от точки входа, указанной в исполняемом файле.</span><span class="sxs-lookup"><span data-stu-id="5a48e-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="5a48e-126">Библиотека DLL сборки образов, загрузчик вызывает [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="5a48e-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="5a48e-127">`_CorExeMain`или `_CorDllMain` выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5a48e-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
-   <span data-ttu-id="5a48e-128">Инициализирует среду CLR.</span><span class="sxs-lookup"><span data-stu-id="5a48e-128">Initializes the CLR.</span></span>  
  
-   <span data-ttu-id="5a48e-129">Находит управляемую точку входа в заголовке CLR сборки.</span><span class="sxs-lookup"><span data-stu-id="5a48e-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
-   <span data-ttu-id="5a48e-130">Начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="5a48e-130">Begins execution.</span></span>  
  
 <span data-ttu-id="5a48e-131">Вызовы загрузчика [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) работать при управлении образов модуля будут выгружены.</span><span class="sxs-lookup"><span data-stu-id="5a48e-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="5a48e-132">Однако эта функция не выполняет никаких действий; он просто возвращает.</span><span class="sxs-lookup"><span data-stu-id="5a48e-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a48e-133">Требования</span><span class="sxs-lookup"><span data-stu-id="5a48e-133">Requirements</span></span>  
 <span data-ttu-id="5a48e-134">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a48e-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a48e-135">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5a48e-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a48e-136">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a48e-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a48e-137">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a48e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a48e-138">См. также</span><span class="sxs-lookup"><span data-stu-id="5a48e-138">See Also</span></span>  
 [<span data-ttu-id="5a48e-139">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="5a48e-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
