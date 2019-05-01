---
title: Метод IMetaDataEmit::DefineMethod
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a67e8ce19a2acf5b4ee1d114858e00d93cb183b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044139"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="7088f-102">Метод IMetaDataEmit::DefineMethod</span><span class="sxs-lookup"><span data-stu-id="7088f-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="7088f-103">Создает определение для метода или глобальной функции с указанной сигнатурой и возвращает маркер для этого определения метода.</span><span class="sxs-lookup"><span data-stu-id="7088f-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7088f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7088f-104">Syntax</span></span>  
  
```  
HRESULT DefineMethod (      
    [in]  mdTypeDef         td,   
    [in]  LPCWSTR           szName,   
    [in]  DWORD             dwMethodFlags,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [in]  ULONG             ulCodeRVA,   
    [in]  DWORD             dwImplFlags,   
    [out] mdMethodDef      *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7088f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7088f-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="7088f-106">[in] `mdTypedef` Маркеров родительского класса или интерфейса родительского метода.</span><span class="sxs-lookup"><span data-stu-id="7088f-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="7088f-107">Задайте `td` для `mdTokenNil`, при определении глобальной функции.</span><span class="sxs-lookup"><span data-stu-id="7088f-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="7088f-108">[in] Имя в формате Юникод.</span><span class="sxs-lookup"><span data-stu-id="7088f-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="7088f-109">[in] Значение [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) перечисление, указывающее атрибуты метода или глобальной функции.</span><span class="sxs-lookup"><span data-stu-id="7088f-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="7088f-110">[in] Сигнатура метода.</span><span class="sxs-lookup"><span data-stu-id="7088f-110">[in] The method signature.</span></span> <span data-ttu-id="7088f-111">Сигнатура сохраняется как предоставляемые.</span><span class="sxs-lookup"><span data-stu-id="7088f-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="7088f-112">Если вам нужно указать дополнительную информацию для любых параметров, используйте [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="7088f-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="7088f-113">[in] Число байт в `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="7088f-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="7088f-114">[in] Адрес кода.</span><span class="sxs-lookup"><span data-stu-id="7088f-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="7088f-115">[in] Значение [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) перечисления, которое указывает возможности реализации метода.</span><span class="sxs-lookup"><span data-stu-id="7088f-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="7088f-116">[out] Токен члена.</span><span class="sxs-lookup"><span data-stu-id="7088f-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7088f-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="7088f-117">Remarks</span></span>  
 <span data-ttu-id="7088f-118">API метаданных гарантирует сохранения методы в порядке их выдает вызывающий объект данного включающего класса или интерфейса, который указан в параметре `td` параметра.</span><span class="sxs-lookup"><span data-stu-id="7088f-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="7088f-119">Дополнительные сведения, касающиеся использования `DefineMethod` и определенных настроек параметров приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="7088f-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="7088f-120">Слоты в таблице V</span><span class="sxs-lookup"><span data-stu-id="7088f-120">Slots in the V-table</span></span>  
 <span data-ttu-id="7088f-121">Среда выполнения использует определения методов для настройки ячеек виртуальной таблицы.</span><span class="sxs-lookup"><span data-stu-id="7088f-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="7088f-122">В случае, когда один или несколько слотов должны быть пропущена, например для сохранения четности в структуре COM-интерфейса пустой метод определен должна занимать одну ячейку или ячейки в v таблице. Задайте `dwMethodFlags` для `mdRTSpecialName` значение [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) перечисления и укажите имя как:</span><span class="sxs-lookup"><span data-stu-id="7088f-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="7088f-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="7088f-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="7088f-124">где *SequenceNumber* регистрационный номер транзакции метода и *числоЯчеек* Число слотов для пропуска в таблице v.</span><span class="sxs-lookup"><span data-stu-id="7088f-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="7088f-125">Если *числоЯчеек* — этот параметр опущен, используется значение 1.</span><span class="sxs-lookup"><span data-stu-id="7088f-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="7088f-126">Эти пустые методы не вызываются в управляемом и неуправляемом коде, и любая попытка их вызова из управляемый или неуправляемый код, создает исключение.</span><span class="sxs-lookup"><span data-stu-id="7088f-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="7088f-127">Единственное их назначение — занять место в v таблице, то среда выполнения создает для COM-интеграции.</span><span class="sxs-lookup"><span data-stu-id="7088f-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="7088f-128">Дублирующиеся методы</span><span class="sxs-lookup"><span data-stu-id="7088f-128">Duplicate Methods</span></span>  
 <span data-ttu-id="7088f-129">Не следует определять повторяющиеся методы.</span><span class="sxs-lookup"><span data-stu-id="7088f-129">You should not define duplicate methods.</span></span> <span data-ttu-id="7088f-130">То есть, не следует вызывать `DefineMethod` с набором повторяющихся значений в `td`, `wzName`, и `pvSig` параметров.</span><span class="sxs-lookup"><span data-stu-id="7088f-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="7088f-131">(Эти три параметра однозначно определяют метод.).</span><span class="sxs-lookup"><span data-stu-id="7088f-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="7088f-132">Тем не менее, можно использовать повторяющиеся тройку условии, что для одного из определений метода, задайте `mdPrivateScope` бит в `dwMethodFlags` параметра.</span><span class="sxs-lookup"><span data-stu-id="7088f-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="7088f-133">( `mdPrivateScope` Бита означает, что компилятор не выдает ссылку на определение этого метода.)</span><span class="sxs-lookup"><span data-stu-id="7088f-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="7088f-134">Сведения о реализации метода</span><span class="sxs-lookup"><span data-stu-id="7088f-134">Method Implementation Information</span></span>  
 <span data-ttu-id="7088f-135">Сведения о реализации метода часто не известны во время объявления.</span><span class="sxs-lookup"><span data-stu-id="7088f-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="7088f-136">Таким образом, не нужно передавать значения в `ulCodeRVA` и `dwImplFlags` параметров при вызове `DefineMethod`.</span><span class="sxs-lookup"><span data-stu-id="7088f-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="7088f-137">Значения могут передаваться в более поздней версии с помощью [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) или [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="7088f-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="7088f-138">В некоторых ситуациях, например вызова неуправляемого кода (PInvoke) или в сценариях COM-взаимодействия, не следует указывать тело метода, и `ulCodeRVA` должно быть равным нулю.</span><span class="sxs-lookup"><span data-stu-id="7088f-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="7088f-139">В этих случаях метод не должен использоваться как абстрактный, так как среда выполнения будет искать реализацию.</span><span class="sxs-lookup"><span data-stu-id="7088f-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="7088f-140">Определение метода для PInvoke</span><span class="sxs-lookup"><span data-stu-id="7088f-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="7088f-141">Для каждой неуправляемой функции, вызываемый посредством PInvoke необходимо определить управляемый метод, представляющий целевую неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="7088f-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="7088f-142">Для определения управляемого метода используется `DefineMethod` с некоторыми параметры, заданные для определенных значений, в зависимости от того, в котором используется PInvoke:</span><span class="sxs-lookup"><span data-stu-id="7088f-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="7088f-143">True PInvoke — включает вызов внешнего неуправляемого метода, который находится в неуправляемой библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="7088f-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="7088f-144">Локальный PInvoke — включает вызов метода машинного неуправляемые, внедренного в текущий управляемый модуль.</span><span class="sxs-lookup"><span data-stu-id="7088f-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="7088f-145">Настройки параметров приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="7088f-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="7088f-146">Параметр</span><span class="sxs-lookup"><span data-stu-id="7088f-146">Parameter</span></span>|<span data-ttu-id="7088f-147">Значения true PInvoke</span><span class="sxs-lookup"><span data-stu-id="7088f-147">Values for true PInvoke</span></span>|<span data-ttu-id="7088f-148">Значения для локальной PInvoke</span><span class="sxs-lookup"><span data-stu-id="7088f-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="7088f-149">Задайте `mdStatic`; Очистить `mdSynchronized` и `mdAbstract`.</span><span class="sxs-lookup"><span data-stu-id="7088f-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="7088f-150">Допустимая распространенных языковой среды исполнения (CLR) сигнатура метода с параметрами, которые являются допустимыми управляемых типов.</span><span class="sxs-lookup"><span data-stu-id="7088f-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="7088f-151">Действительная подпись метода среды CLR с параметрами, которые являются допустимыми управляемых типов.</span><span class="sxs-lookup"><span data-stu-id="7088f-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="7088f-152">0</span><span class="sxs-lookup"><span data-stu-id="7088f-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="7088f-153">Задайте `miCil` и `miManaged`.</span><span class="sxs-lookup"><span data-stu-id="7088f-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="7088f-154">Задайте `miNative` и `miUnmanaged`.</span><span class="sxs-lookup"><span data-stu-id="7088f-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7088f-155">Требования</span><span class="sxs-lookup"><span data-stu-id="7088f-155">Requirements</span></span>  
 <span data-ttu-id="7088f-156">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7088f-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7088f-157">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7088f-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7088f-158">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7088f-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7088f-159">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7088f-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7088f-160">См. также</span><span class="sxs-lookup"><span data-stu-id="7088f-160">See also</span></span>

- [<span data-ttu-id="7088f-161">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7088f-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7088f-162">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="7088f-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
