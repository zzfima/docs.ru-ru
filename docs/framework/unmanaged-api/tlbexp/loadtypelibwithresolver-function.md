---
title: "Функция LoadTypeLibWithResolver"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadTypeLibWithResolver
api_location: TlbRef.dll
api_type: DLLExport
f1_keywords: LoadTypeLibWithResolver
helpviewer_keywords: LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f069d09f25575c39db097024384ad1bf14eaaf02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="1cd25-102">Функция LoadTypeLibWithResolver</span><span class="sxs-lookup"><span data-stu-id="1cd25-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="1cd25-103">Загружает библиотеку типов и использует предоставленный [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) для разрешения любых типов, на которые библиотек.</span><span class="sxs-lookup"><span data-stu-id="1cd25-103">Loads a type library and uses the supplied [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cd25-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1cd25-104">Syntax</span></span>  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1cd25-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1cd25-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="1cd25-106">[in] Путь к файлу библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="1cd25-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="1cd25-107">[in] Объект [REGKIND перечисления](https://msdn.microsoft.com/library/windows/desktop/ms221159.aspx) флаг, который определяет, как библиотека типов зарегистрирована.</span><span class="sxs-lookup"><span data-stu-id="1cd25-107">[in] A [REGKIND enumeration](https://msdn.microsoft.com/library/windows/desktop/ms221159.aspx) flag that controls how the type library is registered.</span></span> <span data-ttu-id="1cd25-108">Его возможными значениями являются:</span><span class="sxs-lookup"><span data-stu-id="1cd25-108">Its possible values are:</span></span>  
  
-   <span data-ttu-id="1cd25-109">`REGKIND_DEFAULT`: Используется поведение по умолчанию при регистрации.</span><span class="sxs-lookup"><span data-stu-id="1cd25-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
-   <span data-ttu-id="1cd25-110">`REGKIND_REGISTER`: Регистрации этой библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="1cd25-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
-   <span data-ttu-id="1cd25-111">`REGKIND_NONE`: Не Регистрируйте Эта библиотека типов.</span><span class="sxs-lookup"><span data-stu-id="1cd25-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="1cd25-112">[in] Указатель на реализацию [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1cd25-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="1cd25-113">[out] Ссылка на библиотеку типов, которая загружается.</span><span class="sxs-lookup"><span data-stu-id="1cd25-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1cd25-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1cd25-114">Return Value</span></span>  
 <span data-ttu-id="1cd25-115">Одно из значений HRESULT, перечисленных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1cd25-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="1cd25-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1cd25-116">Return value</span></span>|<span data-ttu-id="1cd25-117">Значение</span><span class="sxs-lookup"><span data-stu-id="1cd25-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="1cd25-118">Выполнено.</span><span class="sxs-lookup"><span data-stu-id="1cd25-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="1cd25-119">Недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="1cd25-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="1cd25-120">Один или несколько указателей являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="1cd25-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="1cd25-121">Один или несколько аргументов являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="1cd25-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="1cd25-122">Функция не удалось записать в файл.</span><span class="sxs-lookup"><span data-stu-id="1cd25-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="1cd25-123">Не удалось открыть системную базу данных регистрации.</span><span class="sxs-lookup"><span data-stu-id="1cd25-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="1cd25-124">Не удалось открыть библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="1cd25-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="1cd25-125">Не удалось загрузить библиотеку типов или DLL.</span><span class="sxs-lookup"><span data-stu-id="1cd25-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cd25-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="1cd25-126">Remarks</span></span>  
 <span data-ttu-id="1cd25-127">[Tlbexp.exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) вызовы `LoadTypeLibWithResolver` функции во время преобразования сборки типа библиотеки.</span><span class="sxs-lookup"><span data-stu-id="1cd25-127">The [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="1cd25-128">Эта функция загружает заданную библиотеку типов с минимальным доступом к реестру.</span><span class="sxs-lookup"><span data-stu-id="1cd25-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="1cd25-129">Затем она анализирует библиотеки типов для библиотеки типов, на которые, каждый из которых необходимо загрузить и добавлены в родительскую библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="1cd25-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="1cd25-130">Перед загрузкой к указанной библиотеке типов, пути к файлу ссылки должны разрешаться в полный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="1cd25-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="1cd25-131">Это обеспечивается за счет [метод ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) , предоставляемая [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), который передается в `pTlbResolver` параметра.</span><span class="sxs-lookup"><span data-stu-id="1cd25-131">This is accomplished through the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="1cd25-132">Если известен полный путь к файлу библиотеки типов, на которую указывает ссылка, `LoadTypeLibWithResolver` функция загружает и добавляет эту библиотеку в родительскую библиотеку типов, создание библиотеки объединенный тип master.</span><span class="sxs-lookup"><span data-stu-id="1cd25-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="1cd25-133">После функции разрешается и загружает все библиотеки типов, на которые, он возвращает ссылку на библиотеку master разрешенный тип в `pptlib` параметра.</span><span class="sxs-lookup"><span data-stu-id="1cd25-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="1cd25-134">`LoadTypeLibWithResolver` Обычно вызывается функция [Tlbexp.exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), который предоставляет собственный внутренний [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) реализацию в `pTlbResolver` параметр.</span><span class="sxs-lookup"><span data-stu-id="1cd25-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="1cd25-135">При вызове метода `LoadTypeLibWithResolver` напрямую, необходимо создать собственные [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) реализации.</span><span class="sxs-lookup"><span data-stu-id="1cd25-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cd25-136">Требования</span><span class="sxs-lookup"><span data-stu-id="1cd25-136">Requirements</span></span>  
 <span data-ttu-id="1cd25-137">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cd25-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cd25-138">**Заголовок:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="1cd25-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="1cd25-139">**Библиотека:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="1cd25-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="1cd25-140">**Версия платформы .NET framework:** 3.5, 3.0, 2.0</span><span class="sxs-lookup"><span data-stu-id="1cd25-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd25-141">См. также</span><span class="sxs-lookup"><span data-stu-id="1cd25-141">See Also</span></span>  
 [<span data-ttu-id="1cd25-142">Вспомогательные функции Tlbexp</span><span class="sxs-lookup"><span data-stu-id="1cd25-142">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 <span data-ttu-id="1cd25-143">[Функция LoadTypeLibEx](https://msdn.microsoft.com/library/windows/desktop/ms221249\(v=vs.85\).aspx)</span><span class="sxs-lookup"><span data-stu-id="1cd25-143">[LoadTypeLibEx Function](https://msdn.microsoft.com/library/windows/desktop/ms221249\(v=vs.85\).aspx)</span></span>
