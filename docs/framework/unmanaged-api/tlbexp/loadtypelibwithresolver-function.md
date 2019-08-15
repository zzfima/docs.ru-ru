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
ms.openlocfilehash: 6b9bec757071a98e085ccdeee3fc66bfc07f52bc
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040165"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="6ab35-102">Функция LoadTypeLibWithResolver</span><span class="sxs-lookup"><span data-stu-id="6ab35-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="6ab35-103">Загружает библиотеку типов и использует предоставляемый [интерфейс итипелибресолвер](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) для разрешения любых библиотек типов, на которые имеются ссылки.</span><span class="sxs-lookup"><span data-stu-id="6ab35-103">Loads a type library and uses the supplied [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ab35-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ab35-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ab35-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6ab35-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="6ab35-106">окне Путь к файлу библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="6ab35-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="6ab35-107">окне Флаг [перечисления регкинд](https://docs.microsoft.com/windows/win32/api/oleauto/ne-oleauto-regkind) , управляющий регистрацией библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="6ab35-107">[in] A [REGKIND enumeration](https://docs.microsoft.com/windows/win32/api/oleauto/ne-oleauto-regkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="6ab35-108">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="6ab35-108">Its possible values are:</span></span>  
  
- <span data-ttu-id="6ab35-109">`REGKIND_DEFAULT`: Использовать поведение регистрации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6ab35-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
- <span data-ttu-id="6ab35-110">`REGKIND_REGISTER`: Зарегистрируйте эту библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="6ab35-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
- <span data-ttu-id="6ab35-111">`REGKIND_NONE`: Не регистрировать эту библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="6ab35-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="6ab35-112">окне Указатель на реализацию [интерфейса итипелибресолвер](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6ab35-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="6ab35-113">заполняет Ссылка на загружаемую библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="6ab35-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ab35-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6ab35-114">Return Value</span></span>  
 <span data-ttu-id="6ab35-115">Одно из значений HRESULT, перечисленных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6ab35-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="6ab35-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6ab35-116">Return value</span></span>|<span data-ttu-id="6ab35-117">Значение</span><span class="sxs-lookup"><span data-stu-id="6ab35-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="6ab35-118">Выполнено.</span><span class="sxs-lookup"><span data-stu-id="6ab35-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="6ab35-119">Недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="6ab35-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="6ab35-120">Один или несколько указателей являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="6ab35-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="6ab35-121">Один или несколько аргументов являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="6ab35-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="6ab35-122">Функции не удалось выполнить запись в файл.</span><span class="sxs-lookup"><span data-stu-id="6ab35-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="6ab35-123">Не удалось открыть базу данных регистрации системы.</span><span class="sxs-lookup"><span data-stu-id="6ab35-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="6ab35-124">Не удалось открыть библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="6ab35-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="6ab35-125">Не удалось загрузить библиотеку типов или библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="6ab35-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ab35-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="6ab35-126">Remarks</span></span>  
 <span data-ttu-id="6ab35-127">[Программа Tlbexp. exe (средство экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) вызывает `LoadTypeLibWithResolver` функцию во время преобразования сборки в библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="6ab35-127">The [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="6ab35-128">Эта функция загружает указанную библиотеку типов с минимальным доступом к реестру.</span><span class="sxs-lookup"><span data-stu-id="6ab35-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="6ab35-129">Затем функция проверяет библиотеку типов для внутренних ссылочных библиотек типов, каждая из которых должна быть загружена и добавлена в родительскую библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="6ab35-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="6ab35-130">Прежде чем можно будет загрузить библиотеку типов, на которую указывает ссылка, путь к файлу ссылки должен быть разрешаться в полный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="6ab35-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="6ab35-131">Это осуществляется с помощью [метода ресолветипелиб](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) , предоставляемого [интерфейсом итипелибресолвер](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), который `pTlbResolver` передается в параметре.</span><span class="sxs-lookup"><span data-stu-id="6ab35-131">This is accomplished through the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="6ab35-132">Если известен полный путь к файлу библиотеки типов, на которую указывает ссылка, `LoadTypeLibWithResolver` функция загружает и добавляет библиотеку типов, на которую указывает ссылка, в родительскую библиотеку типов, создавая объединенную библиотеку типов Master.</span><span class="sxs-lookup"><span data-stu-id="6ab35-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="6ab35-133">После того как функция разрешает и загружает все библиотеки типов, на которые имеются ссылки, она возвращает ссылку на библиотеку разрешенных шаблонов в `pptlib` параметре.</span><span class="sxs-lookup"><span data-stu-id="6ab35-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="6ab35-134">Функция обычно вызывается программой [Tlbexp. exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), которая предоставляет собственную внутреннюю реализацию `pTlbResolver` [интерфейса итипелибресолвер](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) в параметре. `LoadTypeLibWithResolver`</span><span class="sxs-lookup"><span data-stu-id="6ab35-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="6ab35-135">При вызове `LoadTypeLibWithResolver` напрямую необходимо предоставить собственную реализацию [интерфейса итипелибресолвер](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6ab35-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ab35-136">Требования</span><span class="sxs-lookup"><span data-stu-id="6ab35-136">Requirements</span></span>  
 <span data-ttu-id="6ab35-137">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ab35-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ab35-138">**Заголовок.** Тлбреф. h</span><span class="sxs-lookup"><span data-stu-id="6ab35-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="6ab35-139">**Библиотечная** Тлбреф. lib</span><span class="sxs-lookup"><span data-stu-id="6ab35-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="6ab35-140">**Версия .NET Framework:** 3,5, 3,0, 2,0</span><span class="sxs-lookup"><span data-stu-id="6ab35-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ab35-141">См. также</span><span class="sxs-lookup"><span data-stu-id="6ab35-141">See also</span></span>

- [<span data-ttu-id="6ab35-142">Вспомогательные функции Tlbexp</span><span class="sxs-lookup"><span data-stu-id="6ab35-142">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="6ab35-143">Функция Лоадтипелибекс</span><span class="sxs-lookup"><span data-stu-id="6ab35-143">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
