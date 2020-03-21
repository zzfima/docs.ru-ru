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
ms.openlocfilehash: 3a6da0e845fa50d090cdf0808b211a5806c40961
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178218"
---
# <a name="_corvalidateimage-function"></a><span data-ttu-id="25604-102">Функция _CorValidateImage</span><span class="sxs-lookup"><span data-stu-id="25604-102">_CorValidateImage Function</span></span>
<span data-ttu-id="25604-103">Проверяет управляемые изображения модулей и уведомляет загрузчик операционной системы после их загрузки.</span><span class="sxs-lookup"><span data-stu-id="25604-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25604-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25604-104">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25604-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="25604-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="25604-106">(в) Указатель на исходное местоположение изображения для проверки в виде управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="25604-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="25604-107">Изображение уже должно быть загружено в память.</span><span class="sxs-lookup"><span data-stu-id="25604-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="25604-108">(в) Имя файла изображения.</span><span class="sxs-lookup"><span data-stu-id="25604-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25604-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="25604-109">Return Value</span></span>  
 <span data-ttu-id="25604-110">Эта функция возвращает стандартные `E_OUTOFMEMORY` `E_UNEXPECTED` `E_FAIL` `E_INVALIDARG`значения, и, а также следующие значения.</span><span class="sxs-lookup"><span data-stu-id="25604-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="25604-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="25604-111">Return value</span></span>|<span data-ttu-id="25604-112">Описание</span><span class="sxs-lookup"><span data-stu-id="25604-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="25604-113">Изображение недействительно.</span><span class="sxs-lookup"><span data-stu-id="25604-113">The image is invalid.</span></span> <span data-ttu-id="25604-114">Это значение имеет HRESULT 0xC000007BL.</span><span class="sxs-lookup"><span data-stu-id="25604-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="25604-115">Изображение действительно.</span><span class="sxs-lookup"><span data-stu-id="25604-115">The image is valid.</span></span> <span data-ttu-id="25604-116">Это значение имеет HRESULT 0x0000000L.</span><span class="sxs-lookup"><span data-stu-id="25604-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25604-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="25604-117">Remarks</span></span>  
 <span data-ttu-id="25604-118">В Windows XP и более поздних версиях загрузчик операционной системы проверяет управляемые модули, изучая бит каталога com Descriptor в общем формате файла объекта (COFF).</span><span class="sxs-lookup"><span data-stu-id="25604-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="25604-119">Набор бита указывает на управляемый модуль.</span><span class="sxs-lookup"><span data-stu-id="25604-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="25604-120">Если погрузчик обнаруживает управляемый модуль, он загружает MsCorEE.dll и вызывает, `_CorValidateImage`который выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="25604-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="25604-121">Подтверждает, что изображение является действительным управляемым модулем.</span><span class="sxs-lookup"><span data-stu-id="25604-121">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="25604-122">Изменяет точку входа в изображении на точку входа в время выполнения общего языка (CLR).</span><span class="sxs-lookup"><span data-stu-id="25604-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="25604-123">Для 64-битных версий Windows изменяет изображение, накотороговое в памяти, преобразовывая его из формата PE32 в формат PE32.</span><span class="sxs-lookup"><span data-stu-id="25604-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="25604-124">Возвращается к погрузчику при загрузке управляемых изображений модуля.</span><span class="sxs-lookup"><span data-stu-id="25604-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="25604-125">Для исполняемых изображений загрузчик операционной системы вызывает [функцию _CorExeMain,](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) независимо от точки входа, указанной в исполняемой.</span><span class="sxs-lookup"><span data-stu-id="25604-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="25604-126">Для сборки DLL-изображений погрузчик вызывает [функцию _CorDllMain.](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)</span><span class="sxs-lookup"><span data-stu-id="25604-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="25604-127">`_CorExeMain`или `_CorDllMain` выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="25604-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="25604-128">Инициализирует CLR.</span><span class="sxs-lookup"><span data-stu-id="25604-128">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="25604-129">Находит управляемую точку входа от заголовка CLR сборки.</span><span class="sxs-lookup"><span data-stu-id="25604-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="25604-130">Начинает исполнение.</span><span class="sxs-lookup"><span data-stu-id="25604-130">Begins execution.</span></span>  
  
 <span data-ttu-id="25604-131">Погрузчик вызывает [функцию _CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) при разгрузке управляемых изображений модуля.</span><span class="sxs-lookup"><span data-stu-id="25604-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="25604-132">Однако эта функция не выполняет никаких действий; он просто возвращается.</span><span class="sxs-lookup"><span data-stu-id="25604-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25604-133">Требования</span><span class="sxs-lookup"><span data-stu-id="25604-133">Requirements</span></span>  
 <span data-ttu-id="25604-134">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25604-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25604-135">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="25604-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25604-136">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="25604-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="25604-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25604-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25604-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="25604-138">See also</span></span>

- [<span data-ttu-id="25604-139">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="25604-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
