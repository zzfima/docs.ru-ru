---
title: Функция LoadTypeLibWithResolver
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51d7cd273aa7a8799a1aac90d828ec81a7670906
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64603269"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="86390-102">Функция LoadTypeLibWithResolver</span><span class="sxs-lookup"><span data-stu-id="86390-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="86390-103">Загружает библиотеку типов и использует предоставленный [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) для разрешения любых типов, на которые библиотек.</span><span class="sxs-lookup"><span data-stu-id="86390-103">Loads a type library and uses the supplied [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86390-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86390-104">Syntax</span></span>  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86390-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86390-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="86390-106">[in] Путь к файлу библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="86390-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="86390-107">[in] Объект [REGKIND перечисления](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) флаг, который определяет, как библиотека типов зарегистрирована.</span><span class="sxs-lookup"><span data-stu-id="86390-107">[in] A [REGKIND enumeration](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="86390-108">Его возможными значениями являются:</span><span class="sxs-lookup"><span data-stu-id="86390-108">Its possible values are:</span></span>  
  
- <span data-ttu-id="86390-109">`REGKIND_DEFAULT`: Используйте поведение по умолчанию регистрации.</span><span class="sxs-lookup"><span data-stu-id="86390-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
- <span data-ttu-id="86390-110">`REGKIND_REGISTER`: Регистрации этой библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="86390-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
- <span data-ttu-id="86390-111">`REGKIND_NONE`: Не Регистрируйте этой библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="86390-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="86390-112">[in] Указатель на реализацию [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span><span class="sxs-lookup"><span data-stu-id="86390-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="86390-113">[out] Ссылка на библиотеку типов, который загружается.</span><span class="sxs-lookup"><span data-stu-id="86390-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86390-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="86390-114">Return Value</span></span>  
 <span data-ttu-id="86390-115">Одно из значений HRESULT, перечисленных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="86390-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="86390-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="86390-116">Return value</span></span>|<span data-ttu-id="86390-117">Значение</span><span class="sxs-lookup"><span data-stu-id="86390-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="86390-118">Выполнено.</span><span class="sxs-lookup"><span data-stu-id="86390-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="86390-119">Недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="86390-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="86390-120">Один или несколько указателей являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="86390-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="86390-121">Один или несколько аргументов являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="86390-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="86390-122">Функция не удалось записать в файл.</span><span class="sxs-lookup"><span data-stu-id="86390-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="86390-123">Не удалось открыть системную базу данных регистрации.</span><span class="sxs-lookup"><span data-stu-id="86390-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="86390-124">Не удалось открыть библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="86390-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="86390-125">Не удается загрузить библиотеку типов или библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="86390-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86390-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="86390-126">Remarks</span></span>  
 <span data-ttu-id="86390-127">[Tlbexp.exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) вызовы `LoadTypeLibWithResolver` функции во время преобразования сборки для типа библиотеки.</span><span class="sxs-lookup"><span data-stu-id="86390-127">The [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="86390-128">Эта функция загружает указанной библиотеки типов с минимальным доступом к реестру.</span><span class="sxs-lookup"><span data-stu-id="86390-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="86390-129">Затем функция проверяет библиотеку типов для библиотеки типов, на которые, каждый из которых необходимо загрузить и добавить в библиотеку типов родительского.</span><span class="sxs-lookup"><span data-stu-id="86390-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="86390-130">Прежде чем можно загрузить библиотеку типов, на которую указывает ссылка, пути к файлу ссылки должны разрешаться в полный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="86390-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="86390-131">Это обеспечивается за счет [метод ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) , предоставляемая [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), который передается в `pTlbResolver` параметра.</span><span class="sxs-lookup"><span data-stu-id="86390-131">This is accomplished through the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="86390-132">Если известно, полный путь к файлу библиотеки типов, на которую указывает ссылка, `LoadTypeLibWithResolver` функция загружает и добавляет эту библиотеку в родительскую библиотеку типов, Создание объединенного главную библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="86390-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="86390-133">После того как функция разрешает и загружает все библиотеки типов, на которые, он возвращает ссылку на библиотеку master разрешенный тип в `pptlib` параметра.</span><span class="sxs-lookup"><span data-stu-id="86390-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="86390-134">`LoadTypeLibWithResolver` Обычно вызывается функция [Tlbexp.exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), который предоставляет свой собственный внутренний [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) реализации в `pTlbResolver` параметр.</span><span class="sxs-lookup"><span data-stu-id="86390-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="86390-135">При вызове метода `LoadTypeLibWithResolver` напрямую, необходимо создать собственные [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) реализации.</span><span class="sxs-lookup"><span data-stu-id="86390-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86390-136">Требования</span><span class="sxs-lookup"><span data-stu-id="86390-136">Requirements</span></span>  
 <span data-ttu-id="86390-137">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86390-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86390-138">**Заголовок.** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="86390-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="86390-139">**Библиотека:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="86390-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="86390-140">**Версии платформы .NET framework:** 3.5, 3.0, 2.0</span><span class="sxs-lookup"><span data-stu-id="86390-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86390-141">См. также</span><span class="sxs-lookup"><span data-stu-id="86390-141">See also</span></span>

- [<span data-ttu-id="86390-142">Вспомогательные функции Tlbexp</span><span class="sxs-lookup"><span data-stu-id="86390-142">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="86390-143">Функция LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="86390-143">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
