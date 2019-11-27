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
ms.openlocfilehash: c46b075341742aac605537a08b762b3cf47ef35b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431807"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="f3eec-102">Метод IMetaDataEmit::DefineMethod</span><span class="sxs-lookup"><span data-stu-id="f3eec-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="f3eec-103">Создает определение для метода или глобальной функции с указанной сигнатурой и возвращает маркер в это определение метода.</span><span class="sxs-lookup"><span data-stu-id="f3eec-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3eec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3eec-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="f3eec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3eec-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f3eec-106">окне Маркер `mdTypedef` родительского класса или родительского интерфейса метода.</span><span class="sxs-lookup"><span data-stu-id="f3eec-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="f3eec-107">Задайте для параметра `td` значение `mdTokenNil`, если вы определяете глобальную функцию.</span><span class="sxs-lookup"><span data-stu-id="f3eec-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="f3eec-108">окне Имя члена в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="f3eec-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="f3eec-109">окне Значение перечисления [кормесодаттр](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) , определяющее атрибуты метода или глобальной функции.</span><span class="sxs-lookup"><span data-stu-id="f3eec-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f3eec-110">окне Сигнатура метода.</span><span class="sxs-lookup"><span data-stu-id="f3eec-110">[in] The method signature.</span></span> <span data-ttu-id="f3eec-111">Подпись сохраняется, как указано.</span><span class="sxs-lookup"><span data-stu-id="f3eec-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="f3eec-112">Если необходимо указать дополнительные сведения для всех параметров, используйте метод [IMetaDataEmit:: сетпарампропс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f3eec-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f3eec-113">окне Число байтов в `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="f3eec-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="f3eec-114">окне Адрес кода.</span><span class="sxs-lookup"><span data-stu-id="f3eec-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="f3eec-115">окне Значение перечисления [кормесодимпл](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) , указывающее функции реализации метода.</span><span class="sxs-lookup"><span data-stu-id="f3eec-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="f3eec-116">заполняет Токен элемента.</span><span class="sxs-lookup"><span data-stu-id="f3eec-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3eec-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3eec-117">Remarks</span></span>  
 <span data-ttu-id="f3eec-118">API метаданных гарантирует сохранение методов в том же порядке, в котором вызывающий объект создает их для данного включающего класса или интерфейса, указанного в параметре `td`.</span><span class="sxs-lookup"><span data-stu-id="f3eec-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="f3eec-119">Дополнительные сведения об использовании `DefineMethod` и определенных параметрах параметров приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="f3eec-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="f3eec-120">Слоты в таблице V-Table</span><span class="sxs-lookup"><span data-stu-id="f3eec-120">Slots in the V-table</span></span>  
 <span data-ttu-id="f3eec-121">Среда выполнения использует определения методов для настройки слотов v-table.</span><span class="sxs-lookup"><span data-stu-id="f3eec-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="f3eec-122">В случае, когда необходимо пропустить один или несколько слотов, например для сохранения четности с помощью макета COM-интерфейса, будет определен фиктивный метод, который занимает область или слоты в таблице v-table. Задайте для `dwMethodFlags` значение `mdRTSpecialName` перечисления [кормесодаттр](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) и укажите имя:</span><span class="sxs-lookup"><span data-stu-id="f3eec-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="f3eec-123">_VtblGap\<*SequenceNumber*>\<\_*каунтофслотс*></span><span class="sxs-lookup"><span data-stu-id="f3eec-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="f3eec-124">где *SequenceNumber* — порядковый номер метода, а *каунтофслотс* — число слотов для пропуска в таблице v-table.</span><span class="sxs-lookup"><span data-stu-id="f3eec-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="f3eec-125">Если *каунтофслотс* опущен, то предполагается значение 1.</span><span class="sxs-lookup"><span data-stu-id="f3eec-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="f3eec-126">Эти фиктивные методы не могут быть вызываемыми из управляемого или неуправляемого кода и любая попытка их вызова из управляемого или неуправляемого кода создает исключение.</span><span class="sxs-lookup"><span data-stu-id="f3eec-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="f3eec-127">Их единственная задача состоит в том, чтобы освободить место в таблице v-table, которую среда выполнения создает для интеграции COM.</span><span class="sxs-lookup"><span data-stu-id="f3eec-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="f3eec-128">Дублирующиеся методы</span><span class="sxs-lookup"><span data-stu-id="f3eec-128">Duplicate Methods</span></span>  
 <span data-ttu-id="f3eec-129">Не следует определять дублирующиеся методы.</span><span class="sxs-lookup"><span data-stu-id="f3eec-129">You should not define duplicate methods.</span></span> <span data-ttu-id="f3eec-130">То есть не следует вызывать `DefineMethod` с повторяющимися наборами значений в параметрах `td`, `wzName`и `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="f3eec-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="f3eec-131">(Эти три параметра вместе уникально определяют метод.)</span><span class="sxs-lookup"><span data-stu-id="f3eec-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="f3eec-132">Однако можно использовать повторяющееся тройное значение, если для одного из определений методов задается бит `mdPrivateScope` в параметре `dwMethodFlags`.</span><span class="sxs-lookup"><span data-stu-id="f3eec-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="f3eec-133">(Бит `mdPrivateScope` означает, что компилятор не будет создавать ссылку на это определение метода.)</span><span class="sxs-lookup"><span data-stu-id="f3eec-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="f3eec-134">Сведения о реализации метода</span><span class="sxs-lookup"><span data-stu-id="f3eec-134">Method Implementation Information</span></span>  
 <span data-ttu-id="f3eec-135">Сведения о реализации метода часто неизвестны во время объявления метода.</span><span class="sxs-lookup"><span data-stu-id="f3eec-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="f3eec-136">Поэтому при вызове `DefineMethod`не нужно передавать значения в параметры `ulCodeRVA` и `dwImplFlags`.</span><span class="sxs-lookup"><span data-stu-id="f3eec-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="f3eec-137">Значения можно указать позже с помощью [IMetaDataEmit:: сетмесодимплфлагс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) или [IMetaDataEmit:: SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md).</span><span class="sxs-lookup"><span data-stu-id="f3eec-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="f3eec-138">В некоторых ситуациях, например при вызове платформы (PInvoke) или в сценариях COM-взаимодействия, тело метода не будет передано, а `ulCodeRVA` должно быть установлено в нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="f3eec-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="f3eec-139">В таких ситуациях метод не должен помечаться как абстрактный, поскольку среда выполнения обнаружит реализацию.</span><span class="sxs-lookup"><span data-stu-id="f3eec-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="f3eec-140">Определение метода для PInvoke</span><span class="sxs-lookup"><span data-stu-id="f3eec-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="f3eec-141">Для вызова каждой неуправляемой функции через PInvoke необходимо определить управляемый метод, представляющий целевую неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="f3eec-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="f3eec-142">Чтобы определить управляемый метод, используйте `DefineMethod` с некоторыми параметрами, заданными определенными значениями, в зависимости от способа использования PInvoke:</span><span class="sxs-lookup"><span data-stu-id="f3eec-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="f3eec-143">True PInvoke — включает вызов внешнего неуправляемого метода, который находится в неуправляемой библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="f3eec-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="f3eec-144">Локальный PInvoke — включает вызов собственного неуправляемого метода, внедренного в текущий управляемый модуль.</span><span class="sxs-lookup"><span data-stu-id="f3eec-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="f3eec-145">Параметры параметров приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f3eec-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="f3eec-146">Параметр</span><span class="sxs-lookup"><span data-stu-id="f3eec-146">Parameter</span></span>|<span data-ttu-id="f3eec-147">Значения для истинного PInvoke</span><span class="sxs-lookup"><span data-stu-id="f3eec-147">Values for true PInvoke</span></span>|<span data-ttu-id="f3eec-148">Значения для локального вызова PInvoke</span><span class="sxs-lookup"><span data-stu-id="f3eec-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="f3eec-149">Задайте `mdStatic`; Очистите `mdSynchronized` и `mdAbstract`.</span><span class="sxs-lookup"><span data-stu-id="f3eec-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="f3eec-150">Допустимая сигнатура метода общеязыковой среды выполнения (CLR) с параметрами, которые являются допустимыми управляемыми типами.</span><span class="sxs-lookup"><span data-stu-id="f3eec-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="f3eec-151">Допустимая сигнатура метода CLR с параметрами, которые являются допустимыми управляемыми типами.</span><span class="sxs-lookup"><span data-stu-id="f3eec-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="f3eec-152">0</span><span class="sxs-lookup"><span data-stu-id="f3eec-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="f3eec-153">Задайте `miCil` и `miManaged`.</span><span class="sxs-lookup"><span data-stu-id="f3eec-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="f3eec-154">Задайте `miNative` и `miUnmanaged`.</span><span class="sxs-lookup"><span data-stu-id="f3eec-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3eec-155">Требования</span><span class="sxs-lookup"><span data-stu-id="f3eec-155">Requirements</span></span>  
 <span data-ttu-id="f3eec-156">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3eec-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3eec-157">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f3eec-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3eec-158">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f3eec-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3eec-159">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3eec-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3eec-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="f3eec-160">See also</span></span>

- [<span data-ttu-id="f3eec-161">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f3eec-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f3eec-162">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f3eec-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
