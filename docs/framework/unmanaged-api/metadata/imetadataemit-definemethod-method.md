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
ms.openlocfilehash: d4f3c95428d6f0f8807e284c5b54582428176511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177666"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="f9b26-102">Метод IMetaDataEmit::DefineMethod</span><span class="sxs-lookup"><span data-stu-id="f9b26-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="f9b26-103">Создает определение для метода или глобальной функции с указанной подписью и возвращает маркер к определению этого метода.</span><span class="sxs-lookup"><span data-stu-id="f9b26-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9b26-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9b26-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f9b26-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9b26-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f9b26-106">(в) Токен `mdTypedef` родительского класса или интерфейс родительского интерфейса метода.</span><span class="sxs-lookup"><span data-stu-id="f9b26-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="f9b26-107">Установите, `td` `mdTokenNil`если вы определяете глобальную функцию.</span><span class="sxs-lookup"><span data-stu-id="f9b26-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="f9b26-108">(в) Имя участника в Unicode.</span><span class="sxs-lookup"><span data-stu-id="f9b26-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="f9b26-109">(в) Значение перечисления [CorMethodAttr,](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) которое определяет атрибуты метода или глобальной функции.</span><span class="sxs-lookup"><span data-stu-id="f9b26-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f9b26-110">(в) Подпись метода.</span><span class="sxs-lookup"><span data-stu-id="f9b26-110">[in] The method signature.</span></span> <span data-ttu-id="f9b26-111">Подпись сохраняется по мере поставки.</span><span class="sxs-lookup"><span data-stu-id="f9b26-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="f9b26-112">Если вам необходимо указать дополнительную информацию по любым параметрам, используйте метод [IMetaDataEmit::SetParamProps.](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)</span><span class="sxs-lookup"><span data-stu-id="f9b26-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f9b26-113">(в) Количество байтов `pvSigBlob`в .</span><span class="sxs-lookup"><span data-stu-id="f9b26-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="f9b26-114">(в) Адрес кода.</span><span class="sxs-lookup"><span data-stu-id="f9b26-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="f9b26-115">(в) Значение перечисления [CorMethodImpl,](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) которое определяет особенности реализации метода.</span><span class="sxs-lookup"><span data-stu-id="f9b26-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="f9b26-116">(ваут) Символ участника.</span><span class="sxs-lookup"><span data-stu-id="f9b26-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9b26-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="f9b26-117">Remarks</span></span>  
 <span data-ttu-id="f9b26-118">API метаданных гарантирует сохранение методов в том же порядке, что и вызывающий абонент, испускающий `td` их для заданного класса или интерфейса, указанного в параметре.</span><span class="sxs-lookup"><span data-stu-id="f9b26-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="f9b26-119">Дополнительная информация `DefineMethod` об использовании и определенных параметрах приведена ниже.</span><span class="sxs-lookup"><span data-stu-id="f9b26-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="f9b26-120">Слоты в V-столе</span><span class="sxs-lookup"><span data-stu-id="f9b26-120">Slots in the V-table</span></span>  
 <span data-ttu-id="f9b26-121">Время выполнения использует определения метода для настройки слотов v-таблицы.</span><span class="sxs-lookup"><span data-stu-id="f9b26-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="f9b26-122">В случае, когда один или несколько слотов необходимо пропустить, например, для сохранения паритета с макетом интерфейса COM, определяется манекен метод, чтобы занять слот или слоты в v-таблице; `dwMethodFlags` установить `mdRTSpecialName` значение перечисления [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) и указать имя как:</span><span class="sxs-lookup"><span data-stu-id="f9b26-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="f9b26-123">_VtblGap\<*количество последовательностей*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="f9b26-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="f9b26-124">где *SequenceNumber* — это номер последовательности метода, а *CountOfSlots* — это количество слотов, которые можно пропустить в v-таблице.</span><span class="sxs-lookup"><span data-stu-id="f9b26-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="f9b26-125">Если *CountOfSlots* опущен, предполагается 1.</span><span class="sxs-lookup"><span data-stu-id="f9b26-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="f9b26-126">Эти методы манекена не поддаются вызову ни из управляемого, ни из неуправляемого кода, и любая попытка вызвать их из управляемого или неуправляемого кода генерирует исключение.</span><span class="sxs-lookup"><span data-stu-id="f9b26-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="f9b26-127">Их единственная цель состоит в том, чтобы занять место в v-таблице, которую генерирует время выполнения для интеграции COM.</span><span class="sxs-lookup"><span data-stu-id="f9b26-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="f9b26-128">Двойные методы</span><span class="sxs-lookup"><span data-stu-id="f9b26-128">Duplicate Methods</span></span>  
 <span data-ttu-id="f9b26-129">Не следует определять дублирующие методы.</span><span class="sxs-lookup"><span data-stu-id="f9b26-129">You should not define duplicate methods.</span></span> <span data-ttu-id="f9b26-130">То есть не стоит `DefineMethod` звонить с дублирующим набором значений в `td`, `wzName`и `pvSig` параметрах.</span><span class="sxs-lookup"><span data-stu-id="f9b26-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="f9b26-131">(Эти три параметра вместе однозначно определяют метод.).</span><span class="sxs-lookup"><span data-stu-id="f9b26-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="f9b26-132">Тем не менее, можно использовать дубликат тройной при условии, что для одного из определений метода вы установите `mdPrivateScope` бит в параметре. `dwMethodFlags`</span><span class="sxs-lookup"><span data-stu-id="f9b26-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="f9b26-133">(Бит `mdPrivateScope` означает, что компилятор не будет излучать ссылку на это определение метода.)</span><span class="sxs-lookup"><span data-stu-id="f9b26-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="f9b26-134">Информация о реализации метода</span><span class="sxs-lookup"><span data-stu-id="f9b26-134">Method Implementation Information</span></span>  
 <span data-ttu-id="f9b26-135">Информация о реализации метода часто неизвестна на момент декларируется методом.</span><span class="sxs-lookup"><span data-stu-id="f9b26-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="f9b26-136">Таким образом, вам не нужно передавать `ulCodeRVA` `dwImplFlags` значения в `DefineMethod`и параметров при вызове .</span><span class="sxs-lookup"><span data-stu-id="f9b26-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="f9b26-137">Значения могут быть поставлены позже через [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) или [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), в случае необходимости.</span><span class="sxs-lookup"><span data-stu-id="f9b26-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="f9b26-138">В некоторых ситуациях, таких как сценарии вызова платформы (PInvoke) или `ulCodeRVA` COM interop, тело метода не будет поставлено и должно быть установлено к нулю.</span><span class="sxs-lookup"><span data-stu-id="f9b26-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="f9b26-139">В таких ситуациях метод не должен быть помечен как абстрактный, так как время выполнения будет находить реализацию.</span><span class="sxs-lookup"><span data-stu-id="f9b26-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="f9b26-140">Определение метода для PInvoke</span><span class="sxs-lookup"><span data-stu-id="f9b26-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="f9b26-141">Для того чтобы каждая неуправляемая функция вызывалась через PInvoke, необходимо определить управляемый метод, представляющий целевую неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="f9b26-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="f9b26-142">Чтобы определить управляемый `DefineMethod` метод, используйте с некоторыми параметрами, установленными для определенных значений, в зависимости от способа использования PInvoke:</span><span class="sxs-lookup"><span data-stu-id="f9b26-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="f9b26-143">True PInvoke - включает в себя вызов внешнего неуправляемого метода, который находится в неуправляемом DLL.</span><span class="sxs-lookup"><span data-stu-id="f9b26-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="f9b26-144">Локальный PInvoke - включает в себя вызов родного неуправляемого метода, встроенного в текущий управляемый модуль.</span><span class="sxs-lookup"><span data-stu-id="f9b26-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="f9b26-145">Параметры приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f9b26-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="f9b26-146">Параметр</span><span class="sxs-lookup"><span data-stu-id="f9b26-146">Parameter</span></span>|<span data-ttu-id="f9b26-147">Значения для истинного PInvoke</span><span class="sxs-lookup"><span data-stu-id="f9b26-147">Values for true PInvoke</span></span>|<span data-ttu-id="f9b26-148">Значения для локального PInvoke</span><span class="sxs-lookup"><span data-stu-id="f9b26-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="f9b26-149">Набор `mdStatic`; ясно `mdSynchronized` `mdAbstract`и .</span><span class="sxs-lookup"><span data-stu-id="f9b26-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="f9b26-150">Допустимая подпись метода общего времени выполнения языка (CLR) с параметрами, которые являются действительными управляемыми типами.</span><span class="sxs-lookup"><span data-stu-id="f9b26-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="f9b26-151">Действующая подпись метода CLR с параметрами, которые являются действительными управляемыми типами.</span><span class="sxs-lookup"><span data-stu-id="f9b26-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="f9b26-152">0</span><span class="sxs-lookup"><span data-stu-id="f9b26-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="f9b26-153">Задайте значения для `miCil` и `miManaged`.</span><span class="sxs-lookup"><span data-stu-id="f9b26-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="f9b26-154">Задайте значения для `miNative` и `miUnmanaged`.</span><span class="sxs-lookup"><span data-stu-id="f9b26-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f9b26-155">Требования</span><span class="sxs-lookup"><span data-stu-id="f9b26-155">Requirements</span></span>  
 <span data-ttu-id="f9b26-156">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9b26-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9b26-157">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f9b26-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f9b26-158">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9b26-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9b26-159">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9b26-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9b26-160">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f9b26-160">See also</span></span>

- [<span data-ttu-id="f9b26-161">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f9b26-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f9b26-162">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f9b26-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
