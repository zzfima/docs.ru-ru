---
title: Функция _CorValidateImage
ms.date: 03/30/2017
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6f1d76ef5cf36bcbab29a33647520663f822798
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770038"
---
# <a name="corvalidateimage-function"></a><span data-ttu-id="49693-102">Функция _CorValidateImage</span><span class="sxs-lookup"><span data-stu-id="49693-102">_CorValidateImage Function</span></span>
<span data-ttu-id="49693-103">Проверяет образы управляемого модуля и уведомляет загрузчик операционной системы, после они были загружены.</span><span class="sxs-lookup"><span data-stu-id="49693-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49693-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49693-104">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49693-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="49693-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="49693-106">[in] Указатель на начальное расположение образа для проверки, как управляемый код.</span><span class="sxs-lookup"><span data-stu-id="49693-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="49693-107">Изображение уже должен быть загружен в память.</span><span class="sxs-lookup"><span data-stu-id="49693-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="49693-108">[in] Имя файла изображения.</span><span class="sxs-lookup"><span data-stu-id="49693-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49693-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="49693-109">Return Value</span></span>  
 <span data-ttu-id="49693-110">Эта функция возвращает стандартные значения `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, и `E_FAIL`, а также следующие значения.</span><span class="sxs-lookup"><span data-stu-id="49693-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="49693-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="49693-111">Return value</span></span>|<span data-ttu-id="49693-112">Описание</span><span class="sxs-lookup"><span data-stu-id="49693-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="49693-113">Недопустимый образ.</span><span class="sxs-lookup"><span data-stu-id="49693-113">The image is invalid.</span></span> <span data-ttu-id="49693-114">Это значение имеет HRESULT 0xC000007BL.</span><span class="sxs-lookup"><span data-stu-id="49693-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="49693-115">Образ является допустимым.</span><span class="sxs-lookup"><span data-stu-id="49693-115">The image is valid.</span></span> <span data-ttu-id="49693-116">Это значение имеет HRESULT 0x00000000L.</span><span class="sxs-lookup"><span data-stu-id="49693-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49693-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="49693-117">Remarks</span></span>  
 <span data-ttu-id="49693-118">В Windows XP и более поздних версий загрузчик операционной системы ищет управляемые модули, проверяя бит каталога дескриптора модели COM в заголовке формате COFF файл общего объекта.</span><span class="sxs-lookup"><span data-stu-id="49693-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="49693-119">Установленный бит обозначает управляемый модуль.</span><span class="sxs-lookup"><span data-stu-id="49693-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="49693-120">При обнаружении управляемый модуль, он загружает библиотеку MsCorEE.dll и вызывает метод `_CorValidateImage`, который выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="49693-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="49693-121">Подтверждает, что образ является допустимым управляемым модулем.</span><span class="sxs-lookup"><span data-stu-id="49693-121">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="49693-122">Заменяет точку входа в образе на точку входа в системе common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="49693-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="49693-123">Для 64-разрядных версиях Windows изменяет образ, находящийся в памяти, путем преобразования его из формата PE32 в формат PE32 +.</span><span class="sxs-lookup"><span data-stu-id="49693-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="49693-124">Возвращает загрузчику при загрузке образов управляемого модуля.</span><span class="sxs-lookup"><span data-stu-id="49693-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="49693-125">Для исполняемых образов загрузчик операционной системы затем вызывает [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) функции, независимо от точки входа, указанной в исполняемом файле.</span><span class="sxs-lookup"><span data-stu-id="49693-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="49693-126">Библиотеки DLL сборки образов, загрузчик вызывает [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="49693-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="49693-127">`_CorExeMain` или `_CorDllMain` выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="49693-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="49693-128">Инициализирует среду CLR.</span><span class="sxs-lookup"><span data-stu-id="49693-128">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="49693-129">Находит управляемую точку входа в заголовке среды CLR сборки.</span><span class="sxs-lookup"><span data-stu-id="49693-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="49693-130">Начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="49693-130">Begins execution.</span></span>  
  
 <span data-ttu-id="49693-131">Вызовы загрузчика [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) функционировать, когда управляемые образы модулей будут выгружены.</span><span class="sxs-lookup"><span data-stu-id="49693-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="49693-132">Тем не менее эта функция не выполняет никаких действий; он просто возвращает.</span><span class="sxs-lookup"><span data-stu-id="49693-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49693-133">Требования</span><span class="sxs-lookup"><span data-stu-id="49693-133">Requirements</span></span>  
 <span data-ttu-id="49693-134">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49693-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49693-135">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="49693-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49693-136">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="49693-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49693-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49693-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49693-138">См. также</span><span class="sxs-lookup"><span data-stu-id="49693-138">See also</span></span>

- [<span data-ttu-id="49693-139">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="49693-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
