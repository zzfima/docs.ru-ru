---
title: Справочник по схеме контрактов данных
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts [WCF], schema reference
ms.assetid: 9ebb0ebe-8166-4c93-980a-7c8f1f38f7c0
ms.openlocfilehash: a4ddaaea2133a8adf5271628f442644194a7f453
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131941"
---
# <a name="data-contract-schema-reference"></a><span data-ttu-id="5fb3e-102">Справочник по схеме контрактов данных</span><span class="sxs-lookup"><span data-stu-id="5fb3e-102">Data Contract Schema Reference</span></span>
<span data-ttu-id="5fb3e-103">В данном разделе описывается подмножество схемы XML (XSD), используемое <xref:System.Runtime.Serialization.DataContractSerializer> для описания типов среды CLR, применяемых для сериализации XML.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-103">This topic describes the subset of the XML Schema (XSD) used by <xref:System.Runtime.Serialization.DataContractSerializer> to describe common language runtime (CLR) types for XML serialization.</span></span>  
  
## <a name="datacontractserializer-mappings"></a><span data-ttu-id="5fb3e-104">DataContractSerializer - сопоставления</span><span class="sxs-lookup"><span data-stu-id="5fb3e-104">DataContractSerializer Mappings</span></span>  
 <span data-ttu-id="5fb3e-105">`DataContractSerializer` Сопоставляет типы CLR с XSD при экспорте метаданных из службы Windows Communication Foundation (WCF), используя конечную точку метаданных или [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-105">The `DataContractSerializer` maps CLR types to XSD when metadata is exported from a Windows Communication Foundation (WCF) service using a metadata endpoint or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="5fb3e-106">Дополнительные сведения см. в разделе [сериализатор контракта данных](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-106">For more information, see [Data Contract Serializer](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md).</span></span>  
  
 <span data-ttu-id="5fb3e-107">`DataContractSerializer` также сопоставляет типы XSD типам среды CLR, когда для доступа к документам WSDL или XSD и создания контрактов данных для служб или клиентов используется Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-107">The `DataContractSerializer` also maps XSD to CLR types when Svcutil.exe is used to access Web Services Description Language (WSDL) or XSD documents and generate data contracts for services or clients.</span></span>  
  
 <span data-ttu-id="5fb3e-108">Сопоставление типам CLR с помощью `DataContractSerializer`может выполняться только для экземпляров схемы XML, удовлетворяющих требованиям, описанным в данном документе.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-108">Only XML Schema instances that conform to requirements stated in this document can be mapped to CLR types using `DataContractSerializer`.</span></span>  
  
### <a name="support-levels"></a><span data-ttu-id="5fb3e-109">Уровни поддержки</span><span class="sxs-lookup"><span data-stu-id="5fb3e-109">Support Levels</span></span>  
 <span data-ttu-id="5fb3e-110">`DataContractSerializer` обеспечивает следующие уровни поддержки для данной функции схемы XML:</span><span class="sxs-lookup"><span data-stu-id="5fb3e-110">The `DataContractSerializer` provides the following levels of support for a given XML Schema feature:</span></span>  
  
-   <span data-ttu-id="5fb3e-111">**Поддерживается**.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-111">**Supported**.</span></span> <span data-ttu-id="5fb3e-112">Существует явное сопоставление этой функции типам и (или) атрибутам CLR с помощью `DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-112">There is explicit mapping from this feature to CLR types or attributes (or both) using `DataContractSerializer`.</span></span>  
  
-   <span data-ttu-id="5fb3e-113">**Пропускается**.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-113">**Ignored**.</span></span> <span data-ttu-id="5fb3e-114">Эта функция используется в схемах, импортируемых `DataContractSerializer`, но не влияет на создание кода.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-114">The feature is allowed in schemas imported by the `DataContractSerializer`, but has no effect on code generation.</span></span>  
  
-   <span data-ttu-id="5fb3e-115">**Запрещено**.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-115">**Forbidden**.</span></span> <span data-ttu-id="5fb3e-116">`DataContractSerializer` не поддерживает импорт схемы с использованием данной функции.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-116">The `DataContractSerializer` does not support importing a schema using the feature.</span></span> <span data-ttu-id="5fb3e-117">Например, при доступе Svcutil.exe к WSDL посредством схемы, использующей данную функцию, доступ осуществляется с помощью <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="5fb3e-117">For example, Svcutil.exe, when accessing a WSDL with a schema that uses such a feature, falls back to using the <xref:System.Xml.Serialization.XmlSerializer> instead.</span></span> <span data-ttu-id="5fb3e-118">Это выполняется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-118">This is by default.</span></span>  
  
## <a name="general-information"></a><span data-ttu-id="5fb3e-119">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="5fb3e-119">General Information</span></span>  
  
-   <span data-ttu-id="5fb3e-120">Пространство имен схемы описывается в разделе [Схема XML](https://go.microsoft.com/fwlink/?LinkId=95475).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-120">The schema namespace is described at [XML Schema](https://go.microsoft.com/fwlink/?LinkId=95475).</span></span> <span data-ttu-id="5fb3e-121">В этом документе используется префикс «xs».</span><span class="sxs-lookup"><span data-stu-id="5fb3e-121">The prefix "xs" is used in this document.</span></span>  
  
-   <span data-ttu-id="5fb3e-122">Атрибуты с пространством имен, отличным от пространства имен схемы, игнорируются.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-122">Any attributes with a non-schema namespace are ignored.</span></span>  
  
-   <span data-ttu-id="5fb3e-123">Любые заметки (за исключением описанных в данном документе) игнорируются.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-123">Any annotations (except for those described in this document) are ignored.</span></span>  
  
### <a name="xsschema-attributes"></a><span data-ttu-id="5fb3e-124">\<xs:schema >: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5fb3e-124">\<xs:schema>: attributes</span></span>  
  
|<span data-ttu-id="5fb3e-125">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5fb3e-125">Attribute</span></span>|<span data-ttu-id="5fb3e-126">DataContract</span><span class="sxs-lookup"><span data-stu-id="5fb3e-126">DataContract</span></span>|  
|---------------|------------------|  
|`attributeFormDefault`|<span data-ttu-id="5fb3e-127">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-127">Ignored.</span></span>|  
|`blockDefault`|<span data-ttu-id="5fb3e-128">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-128">Ignored.</span></span>|  
|`elementFormDefault`|<span data-ttu-id="5fb3e-129">Должен иметь полное имя.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-129">Must be qualified.</span></span> <span data-ttu-id="5fb3e-130">Для того чтобы схема поддерживалась `DataContractSerializer`, все элементы должны иметь полное имя.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-130">All elements must be qualified for a schema to be supported by `DataContractSerializer`.</span></span> <span data-ttu-id="5fb3e-131">Это можно сделать, либо присвоив xs:schema/@elementFormDefault «qualified» или установив xs:element/@form до «qualified» в объявлении каждого отдельного элемента.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-131">This can be accomplished by either setting xs:schema/@elementFormDefault to "qualified" or by setting xs:element/@form to "qualified" on each individual element declaration.</span></span>|  
|`finalDefault`|<span data-ttu-id="5fb3e-132">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-132">Ignored.</span></span>|  
|`Id`|<span data-ttu-id="5fb3e-133">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-133">Ignored.</span></span>|  
|`targetNamespace`|<span data-ttu-id="5fb3e-134">Поддерживается и сопоставляется пространству имен контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-134">Supported and mapped to the data contract namespace.</span></span> <span data-ttu-id="5fb3e-135">Если данный атрибут не определен, используется пустое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-135">If this attribute is not specified, the blank namespace is used.</span></span> <span data-ttu-id="5fb3e-136">Не может быть зарезервированному пространству имен `http://schemas.microsoft.com/2003/10/Serialization/`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-136">Cannot be the reserved namespace `http://schemas.microsoft.com/2003/10/Serialization/`.</span></span>|  
|`version`|<span data-ttu-id="5fb3e-137">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-137">Ignored.</span></span>|  
  
### <a name="xsschema-contents"></a><span data-ttu-id="5fb3e-138">\<xs:schema >: содержимое</span><span class="sxs-lookup"><span data-stu-id="5fb3e-138">\<xs:schema>: contents</span></span>  
  
|<span data-ttu-id="5fb3e-139">Описание</span><span class="sxs-lookup"><span data-stu-id="5fb3e-139">Contents</span></span>|<span data-ttu-id="5fb3e-140">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-140">Schema</span></span>|  
|--------------|------------|  
|`include`|<span data-ttu-id="5fb3e-141">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-141">Supported.</span></span> `DataContractSerializer` <span data-ttu-id="5fb3e-142">поддерживает xs: включают и xs: import.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-142">supports xs:include and xs:import.</span></span> <span data-ttu-id="5fb3e-143">Однако при загрузке метаданных из локального файла средство Svcutil.exe ограничивает следование ссылкам `xs:include/@schemaLocation` и `xs:import/@location` .</span><span class="sxs-lookup"><span data-stu-id="5fb3e-143">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="5fb3e-144">В этом случае список файлов схемы должен передаваться по нештатному механизму, а не посредством `include` ; документы схемы, переданные посредством `include`, не учитываются.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-144">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|  
|`redefine`|<span data-ttu-id="5fb3e-145">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-145">Forbidden.</span></span> <span data-ttu-id="5fb3e-146">Использование `xs:redefine` запрещено `DataContractSerializer` по соображениям безопасности: для `x:redefine` требуется следовать `schemaLocation` .</span><span class="sxs-lookup"><span data-stu-id="5fb3e-146">The use of `xs:redefine` is forbidden by `DataContractSerializer` for security reasons: `x:redefine` requires `schemaLocation` to be followed.</span></span> <span data-ttu-id="5fb3e-147">В некоторых случаях Svcutil.exe, использующее DataContract, ограничивает применение `schemaLocation`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-147">In certain circumstances, Svcutil.exe using DataContract restricts use of `schemaLocation`.</span></span>|  
|`import`|<span data-ttu-id="5fb3e-148">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-148">Supported.</span></span> `DataContractSerializer` <span data-ttu-id="5fb3e-149">поддерживает `xs:include` и `xs:import`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-149">supports `xs:include` and `xs:import`.</span></span> <span data-ttu-id="5fb3e-150">Однако при загрузке метаданных из локального файла средство Svcutil.exe ограничивает следование ссылкам `xs:include/@schemaLocation` и `xs:import/@location` .</span><span class="sxs-lookup"><span data-stu-id="5fb3e-150">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="5fb3e-151">В этом случае список файлов схемы должен передаваться по нештатному механизму, а не посредством `include` ; документы схемы, переданные посредством `include`, не учитываются.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-151">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|  
|`simpleType`|<span data-ttu-id="5fb3e-152">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-152">Supported.</span></span> <span data-ttu-id="5fb3e-153">См. раздел `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="5fb3e-153">See the `xs:simpleType` section.</span></span>|  
|`complexType`|<span data-ttu-id="5fb3e-154">Поддерживается, сопоставляется контрактам данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-154">Supported, maps to data contracts.</span></span> <span data-ttu-id="5fb3e-155">См. раздел `xs:complexType` .</span><span class="sxs-lookup"><span data-stu-id="5fb3e-155">See the `xs:complexType` section.</span></span>|  
|`group`|<span data-ttu-id="5fb3e-156">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-156">Ignored.</span></span> `DataContractSerializer` <span data-ttu-id="5fb3e-157">не поддерживает использование `xs:group`, `xs:attributeGroup`, и `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-157">does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="5fb3e-158">Эти объявления игнорируются как дочерние элементы `xs:schema`, но ссылки на них невозможны из `complexType` или других поддерживаемых конструкторов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-158">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`attributeGroup`|<span data-ttu-id="5fb3e-159">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-159">Ignored.</span></span> `DataContractSerializer` <span data-ttu-id="5fb3e-160">не поддерживает использование `xs:group`, `xs:attributeGroup`, и `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-160">does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="5fb3e-161">Эти объявления игнорируются как дочерние элементы `xs:schema`, но ссылки на них невозможны из `complexType` или других поддерживаемых конструкторов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-161">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`element`|<span data-ttu-id="5fb3e-162">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-162">Supported.</span></span> <span data-ttu-id="5fb3e-163">См. «Объявление глобального элемента».</span><span class="sxs-lookup"><span data-stu-id="5fb3e-163">See Global Element Declaration (GED).</span></span>|  
|`attribute`|<span data-ttu-id="5fb3e-164">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-164">Ignored.</span></span> `DataContractSerializer` <span data-ttu-id="5fb3e-165">не поддерживает использование `xs:group`, `xs:attributeGroup`, и `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-165">does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="5fb3e-166">Эти объявления игнорируются как дочерние элементы `xs:schema`, но ссылки на них невозможны из `complexType` или других поддерживаемых конструкторов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-166">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`notation`|<span data-ttu-id="5fb3e-167">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-167">Ignored.</span></span>|  
  
## <a name="complex-types--xscomplextype"></a><span data-ttu-id="5fb3e-168">Сложные типы – \<xs: complexType ></span><span class="sxs-lookup"><span data-stu-id="5fb3e-168">Complex Types – \<xs:complexType></span></span>  
  
### <a name="general-information"></a><span data-ttu-id="5fb3e-169">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="5fb3e-169">General Information</span></span>  
 <span data-ttu-id="5fb3e-170">Каждый сложный тип \<xs: complexType > сопоставляется контракту данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-170">Each complex type \<xs:complexType> maps to a data contract.</span></span>  
  
### <a name="xscomplextype-attributes"></a><span data-ttu-id="5fb3e-171">\<xs: complexType >: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5fb3e-171">\<xs:complexType>: attributes</span></span>  
  
|<span data-ttu-id="5fb3e-172">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5fb3e-172">Attribute</span></span>|<span data-ttu-id="5fb3e-173">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-173">Schema</span></span>|  
|---------------|------------|  
|`abstract`|<span data-ttu-id="5fb3e-174">По умолчанию должен иметь значение false.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-174">Must be false (default).</span></span>|  
|`block`|<span data-ttu-id="5fb3e-175">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-175">Forbidden.</span></span>|  
|`final`|<span data-ttu-id="5fb3e-176">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-176">Ignored.</span></span>|  
|`id`|<span data-ttu-id="5fb3e-177">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-177">Ignored.</span></span>|  
|`mixed`|<span data-ttu-id="5fb3e-178">По умолчанию должен иметь значение false.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-178">Must be false (default).</span></span>|  
|`name`|<span data-ttu-id="5fb3e-179">Поддерживается и сопоставляется имени контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-179">Supported and mapped to the data contract name.</span></span> <span data-ttu-id="5fb3e-180">Если в имени имеются точки, выполняется попытка сопоставить тип внутреннему типу.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-180">If there are periods in the name, an attempt is made to map the type to an inner type.</span></span> <span data-ttu-id="5fb3e-181">Например, сложный тип с именем `A.B` сопоставляется контракту данных, который является внутренним типом для типа с именем контракта данных `A`, но только в том случае, если данный контракт данных существует.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-181">For example, a complex type named `A.B` maps to a data contract type that is an inner type of a type with the data contract name `A`, but only if such a data contract type exists.</span></span> <span data-ttu-id="5fb3e-182">Может существовать более одного уровня вложения: например, `A.B.C` может быть внутренним типом, но только при условии, что и `A` , и `A.B` существуют.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-182">More than one level of nesting is possible: for example, `A.B.C` can be an inner type, but only if `A` and `A.B` both exist.</span></span>|  
  
### <a name="xscomplextype-contents"></a><span data-ttu-id="5fb3e-183">\<xs: complexType >: содержимое</span><span class="sxs-lookup"><span data-stu-id="5fb3e-183">\<xs:complexType>: contents</span></span>  
  
|<span data-ttu-id="5fb3e-184">Описание</span><span class="sxs-lookup"><span data-stu-id="5fb3e-184">Contents</span></span>|<span data-ttu-id="5fb3e-185">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-185">Schema</span></span>|  
|--------------|------------|  
|`simpleContent`|<span data-ttu-id="5fb3e-186">Расширения запрещены.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-186">Extensions are forbidden.</span></span><br /><br /> <span data-ttu-id="5fb3e-187">Ограничение разрешено только из `anySimpleType`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-187">Restriction is allowed only from `anySimpleType`.</span></span>|  
|`complexContent`|<span data-ttu-id="5fb3e-188">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-188">Supported.</span></span> <span data-ttu-id="5fb3e-189">См. «Наследование».</span><span class="sxs-lookup"><span data-stu-id="5fb3e-189">See "Inheritance".</span></span>|  
|`group`|<span data-ttu-id="5fb3e-190">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-190">Forbidden.</span></span>|  
|`all`|<span data-ttu-id="5fb3e-191">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-191">Forbidden.</span></span>|  
|`choice`|<span data-ttu-id="5fb3e-192">Запрещено</span><span class="sxs-lookup"><span data-stu-id="5fb3e-192">Forbidden</span></span>|  
|`sequence`|<span data-ttu-id="5fb3e-193">Поддерживается, сопоставляется членам данных контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-193">Supported, maps to data members of a data contract.</span></span>|  
|`attribute`|<span data-ttu-id="5fb3e-194">Запрещено, даже если use="prohibited" (существует одно исключение).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-194">Forbidden, even if use="prohibited" (with one exception).</span></span> <span data-ttu-id="5fb3e-195">Только необязательные атрибуты из стандартного пространства имен сериализации поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-195">Only optional attributes from the Standard Serialization Schema namespace are supported.</span></span> <span data-ttu-id="5fb3e-196">Они не сопоставляются членам данных в модели программирования контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-196">They do not map to data members in the data contract programming model.</span></span> <span data-ttu-id="5fb3e-197">В настоящее время только один подобный атрибут имеет значение; он рассматривается в разделе ISerializable.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-197">Currently, only one such attribute has meaning and is discussed in the ISerializable section.</span></span> <span data-ttu-id="5fb3e-198">Другие атрибуты игнорируются.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-198">All others are ignored.</span></span>|  
|`attributeGroup`|<span data-ttu-id="5fb3e-199">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-199">Forbidden.</span></span> <span data-ttu-id="5fb3e-200">В выпуске версии 1 WCF `DataContractSerializer` игнорирует наличие `attributeGroup` внутри `xs:complexType`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-200">In the WCF v1 release, `DataContractSerializer` ignores the presence of `attributeGroup` inside `xs:complexType`.</span></span>|  
|`anyAttribute`|<span data-ttu-id="5fb3e-201">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-201">Forbidden.</span></span>|  
|<span data-ttu-id="5fb3e-202">(пусто)</span><span class="sxs-lookup"><span data-stu-id="5fb3e-202">(empty)</span></span>|<span data-ttu-id="5fb3e-203">Сопоставляется с контрактом данных, не имеющем элементов данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-203">Maps to a data contract with no data members.</span></span>|  
  
### <a name="xssequence-in-a-complex-type-attributes"></a><span data-ttu-id="5fb3e-204">\<xs: Sequence > в сложном типе: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5fb3e-204">\<xs:sequence> in a complex type: attributes</span></span>  
  
|<span data-ttu-id="5fb3e-205">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5fb3e-205">Attribute</span></span>|<span data-ttu-id="5fb3e-206">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-206">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="5fb3e-207">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-207">Ignored.</span></span>|  
|`maxOccurs`|<span data-ttu-id="5fb3e-208">По умолчанию должен иметь значение 1.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-208">Must be 1 (default).</span></span>|  
|`minOccurs`|<span data-ttu-id="5fb3e-209">По умолчанию должен иметь значение 1.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-209">Must be 1 (default).</span></span>|  
  
### <a name="xssequence-in-a-complex-type-contents"></a><span data-ttu-id="5fb3e-210">\<xs: Sequence > в сложном типе: содержимое</span><span class="sxs-lookup"><span data-stu-id="5fb3e-210">\<xs:sequence> in a complex type: contents</span></span>  
  
|<span data-ttu-id="5fb3e-211">Описание</span><span class="sxs-lookup"><span data-stu-id="5fb3e-211">Contents</span></span>|<span data-ttu-id="5fb3e-212">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-212">Schema</span></span>|  
|--------------|------------|  
|`element`|<span data-ttu-id="5fb3e-213">Каждый экземпляр сопоставляется с элементом данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-213">Each instance maps to a data member.</span></span>|  
|`group`|<span data-ttu-id="5fb3e-214">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-214">Forbidden.</span></span>|  
|`choice`|<span data-ttu-id="5fb3e-215">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-215">Forbidden.</span></span>|  
|`sequence`|<span data-ttu-id="5fb3e-216">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-216">Forbidden.</span></span>|  
|`any`|<span data-ttu-id="5fb3e-217">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-217">Forbidden.</span></span>|  
|<span data-ttu-id="5fb3e-218">(пусто)</span><span class="sxs-lookup"><span data-stu-id="5fb3e-218">(empty)</span></span>|<span data-ttu-id="5fb3e-219">Сопоставляется с контрактом данных, не имеющем элементов данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-219">Maps to a data contract with no data members.</span></span>|  
  
## <a name="elements--xselement"></a><span data-ttu-id="5fb3e-220">Элементы- \<xs: element ></span><span class="sxs-lookup"><span data-stu-id="5fb3e-220">Elements – \<xs:element></span></span>  
  
### <a name="general-information"></a><span data-ttu-id="5fb3e-221">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="5fb3e-221">General Information</span></span>  
 `<xs:element>` <span data-ttu-id="5fb3e-222">может возникнуть в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="5fb3e-222">can occur in the following contexts:</span></span>  
  
-   <span data-ttu-id="5fb3e-223">Он может использоваться в `<xs:sequence>`, описывающей член данных обычного контракта данных (не коллекции).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-223">It can occur within an `<xs:sequence>`, which describes a data member of a regular (non-collection) data contract.</span></span> <span data-ttu-id="5fb3e-224">В этом случае атрибут `maxOccurs` должен быть равен 1.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-224">In this case, the `maxOccurs` attribute must be 1.</span></span> <span data-ttu-id="5fb3e-225">(Значение 0 недопустимо).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-225">(A value of 0 is not allowed).</span></span>  
  
-   <span data-ttu-id="5fb3e-226">Он может использоваться в `<xs:sequence>`, описывающей член данных контракта данных коллекции.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-226">It can occur within an `<xs:sequence>`, which describes a data member of a collection data contract.</span></span> <span data-ttu-id="5fb3e-227">В этом случае атрибут `maxOccurs` должен иметь значение больше 1 или unbounded.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-227">In this case, the `maxOccurs` attribute must be greater than 1 or "unbounded".</span></span>  
  
-   <span data-ttu-id="5fb3e-228">Он может использоваться в `<xs:schema>` в качестве объявления глобального элемента.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-228">It can occur within an `<xs:schema>` as a Global Element Declaration (GED).</span></span>  
  
### <a name="xselement-with-maxoccurs1-within-an-xssequence-data-members"></a><span data-ttu-id="5fb3e-229">\<xs: element > при maxOccurs = 1 в \<xs: Sequence > (члены данных)</span><span class="sxs-lookup"><span data-stu-id="5fb3e-229">\<xs:element> with maxOccurs=1 within an \<xs:sequence> (Data Members)</span></span>  
  
|<span data-ttu-id="5fb3e-230">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5fb3e-230">Attribute</span></span>|<span data-ttu-id="5fb3e-231">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-231">Schema</span></span>|  
|---------------|------------|  
|`ref`|<span data-ttu-id="5fb3e-232">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-232">Forbidden.</span></span>|  
|`name`|<span data-ttu-id="5fb3e-233">Поддерживается, сопоставляется с именем элемента данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-233">Supported, maps to the data member name.</span></span>|  
|`type`|<span data-ttu-id="5fb3e-234">Поддерживается, сопоставляется типу члена данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-234">Supported, maps to the data member type.</span></span> <span data-ttu-id="5fb3e-235">Дополнительные сведения см. в разделе «Сопоставление тип-примитив».</span><span class="sxs-lookup"><span data-stu-id="5fb3e-235">For more information, see Type/primitive mapping.</span></span> <span data-ttu-id="5fb3e-236">Если не задан (и элемент не содержит анонимный тип), предполагается `xs:anyType` .</span><span class="sxs-lookup"><span data-stu-id="5fb3e-236">If not specified (and the element does not contain an anonymous type), `xs:anyType` is assumed.</span></span>|  
|`block`|<span data-ttu-id="5fb3e-237">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-237">Ignored.</span></span>|  
|`default`|<span data-ttu-id="5fb3e-238">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-238">Forbidden.</span></span>|  
|`fixed`|<span data-ttu-id="5fb3e-239">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-239">Forbidden.</span></span>|  
|`form`|<span data-ttu-id="5fb3e-240">Должен иметь полное имя.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-240">Must be qualified.</span></span> <span data-ttu-id="5fb3e-241">Этот атрибут может быть задан через `elementFormDefault` в `xs:schema`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-241">This attribute can be set through `elementFormDefault` on `xs:schema`.</span></span>|  
|`id`|<span data-ttu-id="5fb3e-242">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-242">Ignored.</span></span>|  
|`maxOccurs`|<span data-ttu-id="5fb3e-243">1</span><span class="sxs-lookup"><span data-stu-id="5fb3e-243">1</span></span>|  
|`minOccurs`|<span data-ttu-id="5fb3e-244">Сопоставляется со свойством <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> элемента данных (`IsRequired` имеет значение true, когда `minOccurs` имеет значение 1).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-244">Maps to the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property of a data member (`IsRequired` is true when `minOccurs` is 1).</span></span>|  
|`nillable`|<span data-ttu-id="5fb3e-245">Влияет на сопоставление типов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-245">Affects type mapping.</span></span> <span data-ttu-id="5fb3e-246">См. "Сопоставление тип-примитив".</span><span class="sxs-lookup"><span data-stu-id="5fb3e-246">See Type/primitive mapping.</span></span>|  
  
### <a name="xselement-with-maxoccurs1-within-an-xssequence-collections"></a><span data-ttu-id="5fb3e-247">\<xs: element > при maxOccurs > 1 в \<xs: Sequence > (коллекции)</span><span class="sxs-lookup"><span data-stu-id="5fb3e-247">\<xs:element> with maxOccurs>1 within an \<xs:sequence> (Collections)</span></span>  
  
-   <span data-ttu-id="5fb3e-248">Сопоставляется <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-248">Maps to a <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span></span>  
  
-   <span data-ttu-id="5fb3e-249">В типах коллекции только один xs:element допустим в xs:sequence.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-249">In collection types, only one xs:element is allowed within an xs:sequence.</span></span>  
  
 <span data-ttu-id="5fb3e-250">Коллекции могут быть следующих типов:</span><span class="sxs-lookup"><span data-stu-id="5fb3e-250">Collections can be of the following types:</span></span>  
  
-   <span data-ttu-id="5fb3e-251">Обычные коллекции (например, массивы).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-251">Regular collections (for example, arrays).</span></span>  
  
-   <span data-ttu-id="5fb3e-252">Коллекции-словари (сопоставляющие одно значение другому; например, <xref:System.Collections.Hashtable>).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-252">Dictionary collections (mapping one value to another; for example, a <xref:System.Collections.Hashtable>).</span></span>  
  
-   <span data-ttu-id="5fb3e-253">Единственное отличие между словарем и массивом типа пара ключ/значение заключается в создаваемой модели программирования.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-253">The only difference between a dictionary and an array of a key/value pair type is in the generated programming model.</span></span> <span data-ttu-id="5fb3e-254">Существует механизм заметки схемы, который можно использовать чтобы указать, что данный тип является коллекцией-словарем.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-254">There is a schema annotation mechanism that can be used to indicate that a given type is a dictionary collection.</span></span>  
  
 <span data-ttu-id="5fb3e-255">Правила для атрибутов `ref`, `block`, `default`, `fixed`, `form`и `id` те же, что и в случае типов, не являющихся коллекциями.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-255">The rules for the `ref`, `block`, `default`, `fixed`, `form`, and `id` attributes are the same as for the non-collection case.</span></span> <span data-ttu-id="5fb3e-256">Другие атрибуты приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-256">Other attributes include those in the following table.</span></span>  
  
|<span data-ttu-id="5fb3e-257">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5fb3e-257">Attribute</span></span>|<span data-ttu-id="5fb3e-258">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-258">Schema</span></span>|  
|---------------|------------|  
|`name`|<span data-ttu-id="5fb3e-259">Поддерживается, сопоставляется свойству <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> в атрибуте `CollectionDataContractAttribute` .</span><span class="sxs-lookup"><span data-stu-id="5fb3e-259">Supported, maps to the <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> property in the `CollectionDataContractAttribute` attribute.</span></span>|  
|`type`|<span data-ttu-id="5fb3e-260">Поддерживается, сопоставляется типу, хранящемуся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-260">Supported, maps to the type stored in the collection.</span></span>|  
|`maxOccurs`|<span data-ttu-id="5fb3e-261">Больше, чем 1 или unbounded.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-261">Greater than 1 or "unbounded".</span></span> <span data-ttu-id="5fb3e-262">Для схемы контроллера домена следует использовать unbounded.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-262">The DC schema should use "unbounded".</span></span>|  
|`minOccurs`|<span data-ttu-id="5fb3e-263">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-263">Ignored.</span></span>|  
|`nillable`|<span data-ttu-id="5fb3e-264">Влияет на сопоставление типов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-264">Affects type mapping.</span></span> <span data-ttu-id="5fb3e-265">Этот атрибут игнорируется в случае коллекций-словарей.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-265">This attribute is ignored for dictionary collections.</span></span>|  
  
### <a name="xselement-within-an-xsschema-global-element-declaration"></a><span data-ttu-id="5fb3e-266">\<xs: element > в \<xs:schema > объявление глобального элемента</span><span class="sxs-lookup"><span data-stu-id="5fb3e-266">\<xs:element> within an \<xs:schema> Global Element Declaration</span></span>  
  
-   <span data-ttu-id="5fb3e-267">Объявление глобального элемента, имеющего то же имя и пространство имен, что и тип в схеме, или определяющего анонимный тип внутри себя, означает связь с типом.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-267">A Global Element Declaration (GED) that has the same name and namespace as a type in schema, or that defines an anonymous type inside itself, is said to be associated with the type.</span></span>  
  
-   <span data-ttu-id="5fb3e-268">Экспорт схемы: связанные объявления глобальных элементов создаются для каждого создаваемого типа, как простого, так и сложного.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-268">Schema export: associated GEDs are generated for every generated type, both simple and complex.</span></span>  
  
-   <span data-ttu-id="5fb3e-269">Десериализация/сериализация: связанные объявления глобальных элементов используются в качестве корневых элементов данного типа.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-269">Deserialization/serialization: associated GEDs are used as root elements for the type.</span></span>  
  
-   <span data-ttu-id="5fb3e-270">Импорт схемы: связанные объявления глобальных элементов не требуются и игнорируются, если они соответствуют следующим правилам (если только они не определяют типы).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-270">Schema import: associated GEDs are not required and are ignored if they follow the following rules (unless they define types).</span></span>  
  
|<span data-ttu-id="5fb3e-271">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5fb3e-271">Attribute</span></span>|<span data-ttu-id="5fb3e-272">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-272">Schema</span></span>|  
|---------------|------------|  
|`abstract`|<span data-ttu-id="5fb3e-273">Должен иметь значение false для связанных объявлений глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-273">Must be false for associated GEDs.</span></span>|  
|`block`|<span data-ttu-id="5fb3e-274">Запрещено в связанных объявлениях глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-274">Forbidden in associated GEDs.</span></span>|  
|`default`|<span data-ttu-id="5fb3e-275">Запрещено в связанных объявлениях глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-275">Forbidden in associated GEDs.</span></span>|  
|`final`|<span data-ttu-id="5fb3e-276">Должен иметь значение false для связанных объявлений глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-276">Must be false for associated GEDs.</span></span>|  
|`fixed`|<span data-ttu-id="5fb3e-277">Запрещено в связанных объявлениях глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-277">Forbidden in associated GEDs.</span></span>|  
|`id`|<span data-ttu-id="5fb3e-278">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-278">Ignored.</span></span>|  
|`name`|<span data-ttu-id="5fb3e-279">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-279">Supported.</span></span> <span data-ttu-id="5fb3e-280">См. определение связанных объявлений глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-280">See the definition of associated GEDs.</span></span>|  
|`nillable`|<span data-ttu-id="5fb3e-281">Должен иметь значение true для связанных объявлений глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-281">Must be true for associated GEDs.</span></span>|  
|`substitutionGroup`|<span data-ttu-id="5fb3e-282">Запрещено в связанных объявлениях глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-282">Forbidden in associated GEDs.</span></span>|  
|`type`|<span data-ttu-id="5fb3e-283">Поддерживается и должен соответствовать связанному типу связанных объявлений глобальных элементов (если только элемент не содержит анонимный тип).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-283">Supported, and must match the associated type for associated GEDs (unless the element contains an anonymous type).</span></span>|  
  
### <a name="xselement-contents"></a><span data-ttu-id="5fb3e-284">\<xs: element >: содержимое</span><span class="sxs-lookup"><span data-stu-id="5fb3e-284">\<xs:element>: contents</span></span>  
  
|<span data-ttu-id="5fb3e-285">Описание</span><span class="sxs-lookup"><span data-stu-id="5fb3e-285">Contents</span></span>|<span data-ttu-id="5fb3e-286">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-286">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="5fb3e-287">Поддерживается.\*</span><span class="sxs-lookup"><span data-stu-id="5fb3e-287">Supported.\*</span></span>|  
|`complexType`|<span data-ttu-id="5fb3e-288">Поддерживается.\*</span><span class="sxs-lookup"><span data-stu-id="5fb3e-288">Supported.\*</span></span>|  
|`unique`|<span data-ttu-id="5fb3e-289">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-289">Ignored.</span></span>|  
|`key`|<span data-ttu-id="5fb3e-290">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-290">Ignored.</span></span>|  
|`keyref`|<span data-ttu-id="5fb3e-291">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-291">Ignored.</span></span>|  
|<span data-ttu-id="5fb3e-292">(пусто)</span><span class="sxs-lookup"><span data-stu-id="5fb3e-292">(blank)</span></span>|<span data-ttu-id="5fb3e-293">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-293">Supported.</span></span>|  
  
 <span data-ttu-id="5fb3e-294">\* При использовании `simpleType` и `complexType,` сопоставления для анонимных типов такое же, как не анонимных типов, тем исключением, что анонимные контракты данных отсутствуют, и поэтому создается именованный контракт с созданным именем на основе имени элемента.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-294">\* When using the `simpleType` and `complexType,` mapping for anonymous types is the same as for non-anonymous types, except that there is no anonymous data contracts, and so a named data contract is created, with a generated name derived from the element name.</span></span> <span data-ttu-id="5fb3e-295">Ниже перечислены правила для анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-295">The rules for anonymous types are in the following list:</span></span>  
  
-   <span data-ttu-id="5fb3e-296">Сведения о реализации WCF: Если `xs:element` имя не содержит точек, анонимный тип сопоставляется внутреннему типу внешнего типа контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-296">WCF implementation detail: If the `xs:element` name does not contain periods, the anonymous type maps to an inner type of the outer data contract type.</span></span> <span data-ttu-id="5fb3e-297">Если имя содержит точки, итоговый тип контракта данных является независимым (не внутренним типом).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-297">If the name contains periods, the resulting data contract type is independent (not an inner type).</span></span>  
  
-   <span data-ttu-id="5fb3e-298">Создаваемое имя контракта данных внутреннего типа - это имя контракта данных внешнего типа, за которым следует точка, имя элемента и строка Type.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-298">The generated data contract name of the inner type is the data contract name of the outer type followed by a period, the name of the element, and the string "Type".</span></span>  
  
-   <span data-ttu-id="5fb3e-299">Если контракт данных с таким именем уже существует, уникальное имя создается путем добавления "1", "2", "3" и т. д., пока не будет создано уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-299">If a data contract with such a name already exists, the name is made unique by appending "1", "2", "3", and so on until a unique name is created.</span></span>  
  
## <a name="simple-types---xssimpletype"></a><span data-ttu-id="5fb3e-300">Простые типы - \<xs:simpleType ></span><span class="sxs-lookup"><span data-stu-id="5fb3e-300">Simple Types - \<xs:simpleType></span></span>  
  
### <a name="xssimpletype-attributes"></a><span data-ttu-id="5fb3e-301">\<xs:simpleType >: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5fb3e-301">\<xs:simpleType>: attributes</span></span>  
  
|<span data-ttu-id="5fb3e-302">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5fb3e-302">Attribute</span></span>|<span data-ttu-id="5fb3e-303">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-303">Schema</span></span>|  
|---------------|------------|  
|`final`|<span data-ttu-id="5fb3e-304">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-304">Ignored.</span></span>|  
|`id`|<span data-ttu-id="5fb3e-305">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-305">Ignored.</span></span>|  
|`name`|<span data-ttu-id="5fb3e-306">Поддерживается, сопоставляется имени контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-306">Supported, maps to the data contract name.</span></span>|  
  
### <a name="xssimpletype-contents"></a><span data-ttu-id="5fb3e-307">\<xs:simpleType >: содержимое</span><span class="sxs-lookup"><span data-stu-id="5fb3e-307">\<xs:simpleType>: contents</span></span>  
  
|<span data-ttu-id="5fb3e-308">Описание</span><span class="sxs-lookup"><span data-stu-id="5fb3e-308">Contents</span></span>|<span data-ttu-id="5fb3e-309">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-309">Schema</span></span>|  
|--------------|------------|  
|`restriction`|<span data-ttu-id="5fb3e-310">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-310">Supported.</span></span> <span data-ttu-id="5fb3e-311">Сопоставляется контрактам данных перечислений.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-311">Maps to enumeration data contracts.</span></span> <span data-ttu-id="5fb3e-312">Если этот атрибут не соответствует шаблону перечисления, он игнорируется.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-312">This attribute is ignored if it does not match the enumeration pattern.</span></span> <span data-ttu-id="5fb3e-313">См. раздел «Ограничения `xs:simpleType` ».</span><span class="sxs-lookup"><span data-stu-id="5fb3e-313">See the `xs:simpleType` restrictions section.</span></span>|  
|`list`|<span data-ttu-id="5fb3e-314">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-314">Supported.</span></span> <span data-ttu-id="5fb3e-315">Сопоставляется контрактам данных перечислений флагов.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-315">Maps to flag enumeration data contracts.</span></span> <span data-ttu-id="5fb3e-316">См. раздел "Списки `xs:simpleType` ".</span><span class="sxs-lookup"><span data-stu-id="5fb3e-316">See the `xs:simpleType` lists section.</span></span>|  
|`union`|<span data-ttu-id="5fb3e-317">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-317">Forbidden.</span></span>|  
  
### <a name="xsrestriction"></a><span data-ttu-id="5fb3e-318">\<xs: Restriction ></span><span class="sxs-lookup"><span data-stu-id="5fb3e-318">\<xs:restriction></span></span>  
  
-   <span data-ttu-id="5fb3e-319">Ограничения сложных типов поддерживаются только для base="`xs:anyType`".</span><span class="sxs-lookup"><span data-stu-id="5fb3e-319">Complex type restrictions are supported only for base="`xs:anyType`".</span></span>  
  
-   <span data-ttu-id="5fb3e-320">Ограничения простых типов `xs:string` , не имеющие никаких других аспектов ограничения, кроме `xs:enumeration` , сопоставляются контрактам данных перечисления.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-320">Simple type restrictions of `xs:string` that do not have any restriction facets other than `xs:enumeration` are mapped to enumeration data contracts.</span></span>  
  
-   <span data-ttu-id="5fb3e-321">Все другие ограничения простых типов сопоставляются типам, которые они ограничивают.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-321">All other simple type restrictions are mapped to the types they restrict.</span></span> <span data-ttu-id="5fb3e-322">Например, ограничение `xs:int` сопоставляется с целым числом так же, как и `xs:int` .</span><span class="sxs-lookup"><span data-stu-id="5fb3e-322">For example, a restriction of `xs:int` maps to an integer, just as `xs:int` itself does.</span></span> <span data-ttu-id="5fb3e-323">Дополнительные сведения о сопоставлении примитивных типов см. в разделе сопоставление тип примитив.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-323">For more information about primitive type mapping, see Type/primitive mapping.</span></span>  
  
### <a name="xsrestriction-attributes"></a><span data-ttu-id="5fb3e-324">\<xs: Restriction >: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5fb3e-324">\<xs:restriction>: attributes</span></span>  
  
|<span data-ttu-id="5fb3e-325">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5fb3e-325">Attribute</span></span>|<span data-ttu-id="5fb3e-326">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-326">Schema</span></span>|  
|---------------|------------|  
|`base`|<span data-ttu-id="5fb3e-327">Должен быть поддерживаемым простым типом или `xs:anyType`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-327">Must be a supported simple type or `xs:anyType`.</span></span>|  
|`id`|<span data-ttu-id="5fb3e-328">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-328">Ignored.</span></span>|  
  
### <a name="xsrestriction-for-all-other-cases-contents"></a><span data-ttu-id="5fb3e-329">\<xs: Restriction > для всех остальных случаев: содержимое</span><span class="sxs-lookup"><span data-stu-id="5fb3e-329">\<xs:restriction> for all other cases: contents</span></span>  
  
|<span data-ttu-id="5fb3e-330">Описание</span><span class="sxs-lookup"><span data-stu-id="5fb3e-330">Contents</span></span>|<span data-ttu-id="5fb3e-331">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-331">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="5fb3e-332">Если существует, должен быть образован от поддерживаемого примитивного типа.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-332">If present, must be derived from a supported primitive type.</span></span>|  
|`minExclusive`|<span data-ttu-id="5fb3e-333">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-333">Ignored.</span></span>|  
|`minInclusive`|<span data-ttu-id="5fb3e-334">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-334">Ignored.</span></span>|  
|`maxExclusive`|<span data-ttu-id="5fb3e-335">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-335">Ignored.</span></span>|  
|`maxInclusive`|<span data-ttu-id="5fb3e-336">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-336">Ignored.</span></span>|  
|`totalDigits`|<span data-ttu-id="5fb3e-337">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-337">Ignored.</span></span>|  
|`fractionDigits`|<span data-ttu-id="5fb3e-338">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-338">Ignored.</span></span>|  
|`length`|<span data-ttu-id="5fb3e-339">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-339">Ignored.</span></span>|  
|`minLength`|<span data-ttu-id="5fb3e-340">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-340">Ignored.</span></span>|  
|`maxLength`|<span data-ttu-id="5fb3e-341">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-341">Ignored.</span></span>|  
|`enumeration`|<span data-ttu-id="5fb3e-342">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-342">Ignored.</span></span>|  
|`whiteSpace`|<span data-ttu-id="5fb3e-343">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-343">Ignored.</span></span>|  
|`pattern`|<span data-ttu-id="5fb3e-344">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-344">Ignored.</span></span>|  
|<span data-ttu-id="5fb3e-345">(пусто)</span><span class="sxs-lookup"><span data-stu-id="5fb3e-345">(blank)</span></span>|<span data-ttu-id="5fb3e-346">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-346">Supported.</span></span>|  
  
## <a name="enumeration"></a><span data-ttu-id="5fb3e-347">Перечисление</span><span class="sxs-lookup"><span data-stu-id="5fb3e-347">Enumeration</span></span>  
  
### <a name="xsrestriction-for-enumerations-attributes"></a><span data-ttu-id="5fb3e-348">\<xs: Restriction > для перечислений: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5fb3e-348">\<xs:restriction> for enumerations: attributes</span></span>  
  
|<span data-ttu-id="5fb3e-349">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5fb3e-349">Attribute</span></span>|<span data-ttu-id="5fb3e-350">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-350">Schema</span></span>|  
|---------------|------------|  
|`base`|<span data-ttu-id="5fb3e-351">Если существует, должен быть `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-351">If present, must be `xs:string`.</span></span>|  
|`id`|<span data-ttu-id="5fb3e-352">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-352">Ignored.</span></span>|  
  
### <a name="xsrestriction-for-enumerations-contents"></a><span data-ttu-id="5fb3e-353">\<xs: Restriction > для перечислений: содержимое</span><span class="sxs-lookup"><span data-stu-id="5fb3e-353">\<xs:restriction> for enumerations: contents</span></span>  
  
|<span data-ttu-id="5fb3e-354">Описание</span><span class="sxs-lookup"><span data-stu-id="5fb3e-354">Contents</span></span>|<span data-ttu-id="5fb3e-355">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-355">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="5fb3e-356">Если существует, должен быть ограничением перечисления, поддерживаемым контрактом данных (этот раздел).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-356">If present, must be an enumeration restriction supported by the data contract (this section).</span></span>|  
|`minExclusive`|<span data-ttu-id="5fb3e-357">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-357">Ignored.</span></span>|  
|`minInclusive`|<span data-ttu-id="5fb3e-358">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-358">Ignored.</span></span>|  
|`maxExclusive`|<span data-ttu-id="5fb3e-359">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-359">Ignored.</span></span>|  
|`maxInclusive`|<span data-ttu-id="5fb3e-360">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-360">Ignored.</span></span>|  
|`totalDigits`|<span data-ttu-id="5fb3e-361">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-361">Ignored.</span></span>|  
|`fractionDigits`|<span data-ttu-id="5fb3e-362">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-362">Ignored.</span></span>|  
|`length`|<span data-ttu-id="5fb3e-363">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-363">Forbidden.</span></span>|  
|`minLength`|<span data-ttu-id="5fb3e-364">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-364">Forbidden.</span></span>|  
|`maxLength`|<span data-ttu-id="5fb3e-365">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-365">Forbidden.</span></span>|  
|`enumeration`|<span data-ttu-id="5fb3e-366">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-366">Supported.</span></span> <span data-ttu-id="5fb3e-367">Перечисление id не учитывается, а value сопоставляется с именем значения в контракте данных перечисления.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-367">Enumeration "id" is ignored, and "value" maps to the value name in the enumeration data contract.</span></span>|  
|`whiteSpace`|<span data-ttu-id="5fb3e-368">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-368">Forbidden.</span></span>|  
|`pattern`|<span data-ttu-id="5fb3e-369">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-369">Forbidden.</span></span>|  
|<span data-ttu-id="5fb3e-370">(пусто)</span><span class="sxs-lookup"><span data-stu-id="5fb3e-370">(empty)</span></span>|<span data-ttu-id="5fb3e-371">Поддерживается, сопоставляется пустому типу перечисления.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-371">Supported, maps to empty enumeration type.</span></span>|  
  
 <span data-ttu-id="5fb3e-372">В следующем коде показан класс перечисления C#.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-372">The following code shows a C# enumeration class.</span></span>  
  
```csharp  
public enum MyEnum  
{  
  first = 3,  
  second = 4,  
  third =5  
}  
```  
  
 <span data-ttu-id="5fb3e-373">`DataContractSerializer`сопоставляет этот класс следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-373">This class maps to the following schema by the `DataContractSerializer`.</span></span> <span data-ttu-id="5fb3e-374">Если значения перечисления начинаются с 1, блоки `xs:annotation` не создаются.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-374">If enumeration values start from 1, `xs:annotation` blocks are not generated.</span></span>  
  
```xml  
<xs:simpleType name="MyEnum">  
<xs:restriction base="xs:string">  
 <xs:enumeration value="first">  
  <xs:annotation>  
   <xs:appinfo>  
    <EnumerationValue   
     xmlns="http://schemas.microsoft.com/2003/10/Serialization/">  
     3  
    </EnumerationValue>  
   </xs:appinfo>  
  </xs:annotation>  
 </xs:enumeration>  
 <xs:enumeration value="second">  
  <xs:annotation>  
   <xs:appinfo>  
    <EnumerationValue   
     xmlns="http://schemas.microsoft.com/2003/10/Serialization/">  
     4  
    </EnumerationValue>  
   </xs:appinfo>  
  </xs:annotation>  
 </xs:enumeration>  
</xs:restriction>  
</xs:simpleType>  
```  
  
### <a name="xslist"></a><span data-ttu-id="5fb3e-375">\<xs:list></span><span class="sxs-lookup"><span data-stu-id="5fb3e-375">\<xs:list></span></span>  
 `DataContractSerializer` <span data-ttu-id="5fb3e-376">типы перечисления карт, отмеченные `System.FlagsAttribute` для `xs:list` производным от `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-376">maps enumeration types marked with `System.FlagsAttribute` to `xs:list` derived from `xs:string`.</span></span> <span data-ttu-id="5fb3e-377">Никакие другие виды `xs:list` не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-377">No other `xs:list` variations are supported.</span></span>  
  
### <a name="xslist-attributes"></a><span data-ttu-id="5fb3e-378">\<xs:list>: attributes</span><span class="sxs-lookup"><span data-stu-id="5fb3e-378">\<xs:list>: attributes</span></span>  
  
|<span data-ttu-id="5fb3e-379">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5fb3e-379">Attribute</span></span>|<span data-ttu-id="5fb3e-380">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-380">Schema</span></span>|  
|---------------|------------|  
|`itemType`|<span data-ttu-id="5fb3e-381">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-381">Forbidden.</span></span>|  
|`id`|<span data-ttu-id="5fb3e-382">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-382">Ignored.</span></span>|  
  
### <a name="xslist-contents"></a><span data-ttu-id="5fb3e-383">\<xs:list>: contents</span><span class="sxs-lookup"><span data-stu-id="5fb3e-383">\<xs:list>: contents</span></span>  
  
|<span data-ttu-id="5fb3e-384">Описание</span><span class="sxs-lookup"><span data-stu-id="5fb3e-384">Contents</span></span>|<span data-ttu-id="5fb3e-385">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-385">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="5fb3e-386">Должен быть ограничением из `xs:string` , использующей аспект `xs:enumeration` .</span><span class="sxs-lookup"><span data-stu-id="5fb3e-386">Must be restriction from `xs:string` using `xs:enumeration` facet.</span></span>|  
  
 <span data-ttu-id="5fb3e-387">Если значение перечисления не является членом последовательности степеней 2 (по умолчанию для флагов), значение помещается в элемент `xs:annotation/xs:appInfo/ser:EnumerationValue` .</span><span class="sxs-lookup"><span data-stu-id="5fb3e-387">If enumeration value does not follow a power of 2 progression (default for Flags), the value is stored in the `xs:annotation/xs:appInfo/ser:EnumerationValue` element.</span></span>  
  
 <span data-ttu-id="5fb3e-388">В следующем коде показана установка флагов для типа перечисления.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-388">For example, the following code flags an enumeration type.</span></span>  
  
```csharp  
[Flags]  
public enum AuthFlags  
{    
  AuthAnonymous = 1,  
  AuthBasic = 2,  
  AuthNTLM = 4,  
  AuthMD5 = 16,  
  AuthWindowsLiveID = 64,  
}  
```  
  
 <span data-ttu-id="5fb3e-389">Этот тип сопоставляется следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-389">This type maps to the following schema.</span></span>  
  
```xml  
<xs:simpleType name="AuthFlags">  
    <xs:list>  
      <xs:simpleType>  
        <xs:restriction base="xs:string">  
          <xs:enumeration value="AuthAnonymous" />  
          <xs:enumeration value="AuthBasic" />  
          <xs:enumeration value="AuthNTLM" />  
          <xs:enumeration value="AuthMD5">  
            <xs:annotation>  
              <xs:appinfo>  
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Se  
rialization/">16</EnumerationValue>  
              </xs:appinfo>  
            </xs:annotation>  
          </xs:enumeration>  
          <xs:enumeration value="AuthWindowsLiveID">  
            <xs:annotation>  
              <xs:appinfo>  
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Se  
rialization/">64</EnumerationValue>  
              </xs:appinfo>  
            </xs:annotation>  
          </xs:enumeration>  
        </xs:restriction>  
      </xs:simpleType>  
    </xs:list>  
  </xs:simpleType>  
```  
  
## <a name="inheritance"></a><span data-ttu-id="5fb3e-390">Наследование</span><span class="sxs-lookup"><span data-stu-id="5fb3e-390">Inheritance</span></span>  
  
### <a name="general-rules"></a><span data-ttu-id="5fb3e-391">Основные правила</span><span class="sxs-lookup"><span data-stu-id="5fb3e-391">General rules</span></span>  
 <span data-ttu-id="5fb3e-392">Контракт данных может наследовать от другого контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-392">A data contract can inherit from another data contract.</span></span> <span data-ttu-id="5fb3e-393">Такие контракты данных сопоставляются базовым и образуются типами расширения с помощью конструктора схемы XML `<xs:extension>` .</span><span class="sxs-lookup"><span data-stu-id="5fb3e-393">Such data contracts map to a base and are derived by extension types using the `<xs:extension>` XML Schema construct.</span></span>  
  
 <span data-ttu-id="5fb3e-394">Контракт данных не может наследовать от контракта данных коллекции.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-394">A data contract cannot inherit from a collection data contract.</span></span>  
  
 <span data-ttu-id="5fb3e-395">В следующем коде показан пример контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-395">For example, the following code is a data contract.</span></span>  
  
```csharp  
[DataContract]  
public class Person  
{  
  [DataMember]  
  public string Name;  
}  
[DataContract]  
public class Employee : Person   
{      
  [DataMember]  
  public int ID;  
}  
```  
  
 <span data-ttu-id="5fb3e-396">Этот контракт данных сопоставляется следующему объявлению типа схемы XML.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-396">This data contract maps to the following XML Schema type declaration.</span></span>  
  
```xml  
<xs:complexType name="Employee">  
 <xs:complexContent mixed="false">  
  <xs:extension base="tns:Person">  
   <xs:sequence>  
    <xs:element minOccurs="0" name="ID" type="xs:int"/>  
   </xs:sequence>  
  </xs:extension>  
 </xs:complexContent>  
</xs:complexType>  
<xs:complexType name="Person">  
 <xs:sequence>  
  <xs:element minOccurs="0" name="Name"   
    nillable="true" type="xs:string"/>  
 </xs:sequence>  
</xs:complexType>  
```  
  
### <a name="xscomplexcontent-attributes"></a><span data-ttu-id="5fb3e-397">\<xs:complexContent >: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5fb3e-397">\<xs:complexContent>: attributes</span></span>  
  
|<span data-ttu-id="5fb3e-398">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5fb3e-398">Attribute</span></span>|<span data-ttu-id="5fb3e-399">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-399">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="5fb3e-400">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-400">Ignored.</span></span>|  
|`mixed`|<span data-ttu-id="5fb3e-401">Должен иметь значение false.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-401">Must be false.</span></span>|  
  
### <a name="xscomplexcontent-contents"></a><span data-ttu-id="5fb3e-402">\<xs:complexContent >: содержимое</span><span class="sxs-lookup"><span data-stu-id="5fb3e-402">\<xs:complexContent>: contents</span></span>  
  
|<span data-ttu-id="5fb3e-403">Описание</span><span class="sxs-lookup"><span data-stu-id="5fb3e-403">Contents</span></span>|<span data-ttu-id="5fb3e-404">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-404">Schema</span></span>|  
|--------------|------------|  
|`restriction`|<span data-ttu-id="5fb3e-405">Запрещено, за исключением случая, когда base="`xs:anyType`".</span><span class="sxs-lookup"><span data-stu-id="5fb3e-405">Forbidden, except when base="`xs:anyType`".</span></span> <span data-ttu-id="5fb3e-406">Последнее эквивалентно помещению содержимого `xs:restriction` прямо под контейнер `xs:complexContent`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-406">The latter is equivalent to placing the content of the `xs:restriction` directly under the container of the `xs:complexContent`.</span></span>|  
|`extension`|<span data-ttu-id="5fb3e-407">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-407">Supported.</span></span> <span data-ttu-id="5fb3e-408">Сопоставляется наследованию контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-408">Maps to data contract inheritance.</span></span>|  
  
### <a name="xsextension-in-xscomplexcontent-attributes"></a><span data-ttu-id="5fb3e-409">\<xs: Extension > в \<xs:complexContent >: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5fb3e-409">\<xs:extension> in \<xs:complexContent>: attributes</span></span>  
  
|<span data-ttu-id="5fb3e-410">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5fb3e-410">Attribute</span></span>|<span data-ttu-id="5fb3e-411">Схема</span><span class="sxs-lookup"><span data-stu-id="5fb3e-411">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="5fb3e-412">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-412">Ignored.</span></span>|  
|`base`|<span data-ttu-id="5fb3e-413">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-413">Supported.</span></span> <span data-ttu-id="5fb3e-414">Сопоставляется базовому типу контракта данных, от которого наследует этот тип.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-414">Maps to the base data contract type that this type inherits from.</span></span>|  
  
### <a name="xsextension-in-xscomplexcontent-contents"></a><span data-ttu-id="5fb3e-415">\<xs: Extension > в \<xs:complexContent >: содержимое</span><span class="sxs-lookup"><span data-stu-id="5fb3e-415">\<xs:extension> in \<xs:complexContent>: contents</span></span>  
 <span data-ttu-id="5fb3e-416">Применяются те же правила, что и для содержимого `<xs:complexType>` .</span><span class="sxs-lookup"><span data-stu-id="5fb3e-416">The rules are the same as for `<xs:complexType>` contents.</span></span>  
  
 <span data-ttu-id="5fb3e-417">Если дается `<xs:sequence>` , ее элементы сопоставляются дополнительным членам данных, присутствующим в производном контракте данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-417">If an `<xs:sequence>` is provided, its member elements map to additional data members that are present in the derived data contract.</span></span>  
  
 <span data-ttu-id="5fb3e-418">Если производный тип содержит элемент с тем же именем, что и элемент базового типа, дублирующееся объявление элемента сопоставляется члену данных с создаваемым уникальным именем.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-418">If a derived type contains an element with the same name as an element in a base type, the duplicate element declaration maps to a data member with a name that is generated to be unique.</span></span> <span data-ttu-id="5fb3e-419">Положительные целые числа добавляются к имени члена данных («member1», «member2» и т. д.) до тех пор, пока не будет найдено уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-419">Positive integer numbers are added to the data member name ("member1", "member2", and so on) until a unique name is found.</span></span> <span data-ttu-id="5fb3e-420">И наоборот:</span><span class="sxs-lookup"><span data-stu-id="5fb3e-420">Conversely:</span></span>  
  
-   <span data-ttu-id="5fb3e-421">Если производный контракт данных имеет член данных с тем же именем и типом, что и член данных в базовом контракте данных, `DataContractSerializer` создает соответствующий элемент в производном типе.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-421">If a derived data contract has a data member with the same name and type as a data member in a base data contract, `DataContractSerializer` generates this corresponding element in the derived type.</span></span>  
  
-   <span data-ttu-id="5fb3e-422">Если производный контракт данных имеет член данных с тем же именем, что и член данных в базовом контракте данных, но другой тип, `DataContractSerializer` импортирует схему с элементом типа `xs:anyType` как в базовый тип, так и в объявления производного типа.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-422">If a derived data contract has a data member with the same name as a data member in a base data contract but a different type, the `DataContractSerializer` imports a schema with an element of the type `xs:anyType` in both base type and derived type declarations.</span></span> <span data-ttu-id="5fb3e-423">Исходное имя типа сохраняется в `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-423">The original type name is preserved in `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span></span>  
  
 <span data-ttu-id="5fb3e-424">В обоих случаях может возникнуть схема с неоднозначной моделью содержимого, которая зависит от порядка соответствующих членов данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-424">Both variations may lead to a schema with an ambiguous content model, which depends on the order of the respective data members.</span></span>  
  
## <a name="typeprimitive-mapping"></a><span data-ttu-id="5fb3e-425">Сопоставление тип-примитив</span><span class="sxs-lookup"><span data-stu-id="5fb3e-425">Type/primitive mapping</span></span>  
 <span data-ttu-id="5fb3e-426">`DataContractSerializer` использует следующие сопоставления для примитивных типов схемы XML.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-426">The `DataContractSerializer` uses the following mapping for XML Schema primitive types.</span></span>  
  
|<span data-ttu-id="5fb3e-427">Тип XSD</span><span class="sxs-lookup"><span data-stu-id="5fb3e-427">XSD type</span></span>|<span data-ttu-id="5fb3e-428">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="5fb3e-428">.NET type</span></span>|  
|--------------|---------------|  
|`anyType`|<xref:System.Object><span data-ttu-id="5fb3e-429">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-429">.</span></span>|  
|`anySimpleType`|<xref:System.String><span data-ttu-id="5fb3e-430">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-430">.</span></span>|  
|`duration`|<xref:System.TimeSpan><span data-ttu-id="5fb3e-431">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-431">.</span></span>|  
|`dateTime`|<xref:System.DateTime><span data-ttu-id="5fb3e-432">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-432">.</span></span>|  
|`dateTimeOffset`|<xref:System.DateTime> <span data-ttu-id="5fb3e-433">и <xref:System.TimeSpan> для смещения.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-433">and <xref:System.TimeSpan> for the offset.</span></span> <span data-ttu-id="5fb3e-434">См. «Сериализация DateTimeOffset» ниже.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-434">See DateTimeOffset Serialization below.</span></span>|  
|`time`|<xref:System.String><span data-ttu-id="5fb3e-435">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-435">.</span></span>|  
|`date`|<xref:System.String><span data-ttu-id="5fb3e-436">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-436">.</span></span>|  
|`gYearMonth`|<xref:System.String><span data-ttu-id="5fb3e-437">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-437">.</span></span>|  
|`gYear`|<xref:System.String><span data-ttu-id="5fb3e-438">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-438">.</span></span>|  
|`gMonthDay`|<xref:System.String><span data-ttu-id="5fb3e-439">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-439">.</span></span>|  
|`gDay`|<xref:System.String><span data-ttu-id="5fb3e-440">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-440">.</span></span>|  
|`gMonth`|<xref:System.String><span data-ttu-id="5fb3e-441">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-441">.</span></span>|  
|`boolean`|<xref:System.Boolean>|  
|`base64Binary`|<xref:System.Byte> <span data-ttu-id="5fb3e-442">Массив.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-442">array.</span></span>|  
|`hexBinary`|<xref:System.String><span data-ttu-id="5fb3e-443">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-443">.</span></span>|  
|`float`|<xref:System.Single><span data-ttu-id="5fb3e-444">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-444">.</span></span>|  
|`double`|<xref:System.Double><span data-ttu-id="5fb3e-445">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-445">.</span></span>|  
|`anyURI`|<xref:System.Uri><span data-ttu-id="5fb3e-446">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-446">.</span></span>|  
|`QName`|<xref:System.Xml.XmlQualifiedName><span data-ttu-id="5fb3e-447">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-447">.</span></span>|  
|`string`|<xref:System.String><span data-ttu-id="5fb3e-448">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-448">.</span></span>|  
|`normalizedString`|<xref:System.String><span data-ttu-id="5fb3e-449">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-449">.</span></span>|  
|`token`|<xref:System.String><span data-ttu-id="5fb3e-450">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-450">.</span></span>|  
|`language`|<xref:System.String><span data-ttu-id="5fb3e-451">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-451">.</span></span>|  
|`Name`|<xref:System.String><span data-ttu-id="5fb3e-452">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-452">.</span></span>|  
|`NCName`|<xref:System.String><span data-ttu-id="5fb3e-453">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-453">.</span></span>|  
|`ID`|<xref:System.String><span data-ttu-id="5fb3e-454">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-454">.</span></span>|  
|`IDREF`|<xref:System.String><span data-ttu-id="5fb3e-455">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-455">.</span></span>|  
|`IDREFS`|<xref:System.String><span data-ttu-id="5fb3e-456">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-456">.</span></span>|  
|`ENTITY`|<xref:System.String><span data-ttu-id="5fb3e-457">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-457">.</span></span>|  
|`ENTITIES`|<xref:System.String><span data-ttu-id="5fb3e-458">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-458">.</span></span>|  
|`NMTOKEN`|<xref:System.String><span data-ttu-id="5fb3e-459">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-459">.</span></span>|  
|`NMTOKENS`|<xref:System.String><span data-ttu-id="5fb3e-460">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-460">.</span></span>|  
|`decimal`|<xref:System.Decimal><span data-ttu-id="5fb3e-461">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-461">.</span></span>|  
|`integer`|<xref:System.Int64><span data-ttu-id="5fb3e-462">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-462">.</span></span>|  
|`nonPositiveInteger`|<xref:System.Int64><span data-ttu-id="5fb3e-463">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-463">.</span></span>|  
|`negativeInteger`|<xref:System.Int64><span data-ttu-id="5fb3e-464">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-464">.</span></span>|  
|`long`|<xref:System.Int64><span data-ttu-id="5fb3e-465">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-465">.</span></span>|  
|`int`|<xref:System.Int32><span data-ttu-id="5fb3e-466">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-466">.</span></span>|  
|`short`|<xref:System.Int16><span data-ttu-id="5fb3e-467">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-467">.</span></span>|  
|`Byte`|<xref:System.SByte><span data-ttu-id="5fb3e-468">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-468">.</span></span>|  
|`nonNegativeInteger`|<xref:System.Int64><span data-ttu-id="5fb3e-469">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-469">.</span></span>|  
|`unsignedLong`|<xref:System.UInt64><span data-ttu-id="5fb3e-470">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-470">.</span></span>|  
|`unsignedInt`|<xref:System.UInt32><span data-ttu-id="5fb3e-471">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-471">.</span></span>|  
|`unsignedShort`|<xref:System.UInt16><span data-ttu-id="5fb3e-472">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-472">.</span></span>|  
|`unsignedByte`|<xref:System.Byte><span data-ttu-id="5fb3e-473">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-473">.</span></span>|  
|`positiveInteger`|<xref:System.Int64><span data-ttu-id="5fb3e-474">.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-474">.</span></span>|  
  
## <a name="iserializable-types-mapping"></a><span data-ttu-id="5fb3e-475">Сопоставление типов ISerializable</span><span class="sxs-lookup"><span data-stu-id="5fb3e-475">ISerializable types mapping</span></span>  
 <span data-ttu-id="5fb3e-476">В [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.0 интерфейс <xref:System.Runtime.Serialization.ISerializable> использовался как основной механизм сериализации объектов для сохранения или передачи данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-476">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] version 1.0, <xref:System.Runtime.Serialization.ISerializable> was introduced as a general mechanism to serialize objects for persistence or data transfer.</span></span> <span data-ttu-id="5fb3e-477">Существует много типов [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] , которые реализуют интерфейс `ISerializable` и могут автоматически передаваться между приложениями.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-477">There are many [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types that implement `ISerializable` and that can be passed between applications.</span></span> <xref:System.Runtime.Serialization.DataContractSerializer> <span data-ttu-id="5fb3e-478">Обычно поддерживает `ISerializable` классы.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-478">naturally provides support for `ISerializable` classes.</span></span> <span data-ttu-id="5fb3e-479">`DataContractSerializer` сопоставляет типы схемы реализации `ISerializable` , отличающиеся только полным именем типа (QName) и фактически являющиеся коллекциями свойств.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-479">The `DataContractSerializer` maps `ISerializable` implementation schema types that differ only by the QName (qualified name) of the type and are effectively property collections.</span></span> <span data-ttu-id="5fb3e-480">Например `DataContractSerializer` сопоставляет <xref:System.Exception> к следующему типу XSD в `http://schemas.datacontract.org/2004/07/System` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-480">For example, the `DataContractSerializer` maps <xref:System.Exception> to the following XSD type in the `http://schemas.datacontract.org/2004/07/System` namespace.</span></span>  
  
```xml  
<xs:complexType name="Exception">  
 <xs:sequence>  
  <xs:any minOccurs="0" maxOccurs="unbounded"   
      namespace="##local" processContents="skip"/>  
 </xs:sequence>  
 <xs:attribute ref="ser:FactoryType"/>  
</xs:complexType>  
```  
  
 <span data-ttu-id="5fb3e-481">Необязательный атрибут `ser:FactoryType` , объявленный в схеме сериализации контракта данных ссылается на класс фабрики, который может выполнить десериализацию типа.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-481">The optional attribute `ser:FactoryType` declared in the Data Contract Serialization schema references a factory class that can deserialize the type.</span></span> <span data-ttu-id="5fb3e-482">Класс фабрики может входить в коллекцию известных типов используемого экземпляра `DataContractSerializer` .</span><span class="sxs-lookup"><span data-stu-id="5fb3e-482">The factory class must be part of the known types collection of the `DataContractSerializer` instance being used.</span></span> <span data-ttu-id="5fb3e-483">Дополнительные сведения об известных типах см. в разделе [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-483">For more information about known types, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="datacontract-serialization-schema"></a><span data-ttu-id="5fb3e-484">DataContract - схема сериализации</span><span class="sxs-lookup"><span data-stu-id="5fb3e-484">DataContract Serialization Schema</span></span>  
 <span data-ttu-id="5fb3e-485">Ряд схем, импортируемых `DataContractSerializer` , использует типы, элементы и атрибуты специального пространства имен сериализации контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-485">A number of schemas exported by the `DataContractSerializer` use types, elements, and attributes from a special Data Contract Serialization namespace:</span></span>  
  
 `http://schemas.microsoft.com/2003/10/Serialization`
  
 <span data-ttu-id="5fb3e-486">Ниже приведен пример полного объявления схемы сериализации контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-486">The following is a complete Data Contract Serialization schema declaration.</span></span>  
  
```xml  
<xs:schema attributeFormDefault="qualified"          
   elementFormDefault="qualified"        
   targetNamespace =   
    "http://schemas.microsoft.com/2003/10/Serialization/"   
   xmlns:xs="http://www.w3.org/2001/XMLSchema"        
   xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/">  
  
 <!-- Top-level elements for primitive types. -->  
 <xs:element name="anyType" nillable="true" type="xs:anyType"/>  
 <xs:element name="anyURI" nillable="true" type="xs:anyURI"/>  
 <xs:element name="base64Binary"  
       nillable="true" type="xs:base64Binary"/>  
 <xs:element name="boolean" nillable="true" type="xs:boolean"/>  
 <xs:element name="byte" nillable="true" type="xs:byte"/>  
 <xs:element name="dateTime" nillable="true" type="xs:dateTime"/>  
 <xs:element name="decimal" nillable="true" type="xs:decimal"/>  
 <xs:element name="double" nillable="true" type="xs:double"/>  
 <xs:element name="float" nillable="true" type="xs:float"/>  
 <xs:element name="int" nillable="true" type="xs:int"/>  
 <xs:element name="long" nillable="true" type="xs:long"/>  
 <xs:element name="QName" nillable="true" type="xs:QName"/>  
 <xs:element name="short" nillable="true" type="xs:short"/>  
 <xs:element name="string" nillable="true" type="xs:string"/>  
 <xs:element name="unsignedByte"  
       nillable="true" type="xs:unsignedByte"/>  
 <xs:element name="unsignedInt"  
       nillable="true" type="xs:unsignedInt"/>  
 <xs:element name="unsignedLong"  
       nillable="true" type="xs:unsignedLong"/>  
 <xs:element name="unsignedShort"  
       nillable="true" type="xs:unsignedShort"/>  
  
 <!-- Primitive types introduced for certain .NET simple types. -->  
 <xs:element name="char" nillable="true" type="tns:char"/>  
 <xs:simpleType name="char">  
  <xs:restriction base="xs:int"/>  
 </xs:simpleType>  
  
 <!-- xs:duration is restricted to an ordered value space,  
    to map to System.TimeSpan -->  
 <xs:element name="duration" nillable="true" type="tns:duration"/>  
 <xs:simpleType name="duration">  
  <xs:restriction base="xs:duration">  
   <xs:pattern   
     value="\-?P(\d*D)?(T(\d*H)?(\d*M)?(\d*(\.\d*)?S)?)?"/>  
   <xs:minInclusive value="-P10675199DT2H48M5.4775808S"/>  
   <xs:maxInclusive value="P10675199DT2H48M5.4775807S"/>  
  </xs:restriction>  
 </xs:simpleType>  
  
 <xs:element name="guid" nillable="true" type="tns:guid"/>  
 <xs:simpleType name="guid">  
  <xs:restriction base="xs:string">  
   <xs:pattern value="[\da-fA-F]{8}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{12}"/>  
  </xs:restriction>  
 </xs:simpleType>  
  
 <!-- This is used for schemas exported from ISerializable type. -->  
 <xs:attribute name="FactoryType" type="xs:QName"/>  
</xs:schema>  
```  
  
 <span data-ttu-id="5fb3e-487">Необходимо отметить следующее.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-487">The following should be noted:</span></span>  
  
-   `ser:char` <span data-ttu-id="5fb3e-488">введен для представления символов Юникода типа <xref:System.Char>.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-488">is introduced to represent Unicode characters of type <xref:System.Char>.</span></span>  
  
-   <span data-ttu-id="5fb3e-489">`valuespace`					`xs:duration` сокращается до упорядоченного набора, чтобы можно было выполнить его сопоставление <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-489">The `valuespace` of `xs:duration` is reduced to an ordered set so that it can be mapped to a <xref:System.TimeSpan>.</span></span>  
  
-   `FactoryType` <span data-ttu-id="5fb3e-490">используется в схемах, экспортируемых из типов, которые являются производными от <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-490">is used in schemas exported from types that are derived from <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
## <a name="importing-non-datacontract-schemas"></a><span data-ttu-id="5fb3e-491">Импорт схем, отличных от DataContract</span><span class="sxs-lookup"><span data-stu-id="5fb3e-491">Importing non-DataContract schemas</span></span>  
 `DataContractSerializer` <span data-ttu-id="5fb3e-492">имеет `ImportXmlTypes` , которая выполняет импорт схем, которые не соответствуют `DataContractSerializer` профилю XSD (см. в разделе <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> свойство).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-492">has the `ImportXmlTypes` option to allow import of schemas that do not conform to the `DataContractSerializer` XSD profile (see the <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> property).</span></span> <span data-ttu-id="5fb3e-493">Если задать этому параметру значение `true` , типы схемы, не удовлетворяющие требованиям, будут приняты и сопоставлены следующей реализации; <xref:System.Xml.Serialization.IXmlSerializable> упакует массив <xref:System.Xml.XmlNode> (отличается только имя класса).</span><span class="sxs-lookup"><span data-stu-id="5fb3e-493">Setting this option to `true` enables acceptance of non-conforming schema types and mapping them to the following implementation, <xref:System.Xml.Serialization.IXmlSerializable> wrapping an array of <xref:System.Xml.XmlNode> (only the class name differs).</span></span>  
  
```csharp  
[GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
[System.Xml.Serialization.XmlSchemaProviderAttribute("ExportSchema")]  
[System.Xml.Serialization.XmlRootAttribute(IsNullable=false)]  
public partial class Person : object, IXmlSerializable  
{    
  private XmlNode[] nodesField;    
  private static XmlQualifiedName typeName =   
new XmlQualifiedName("Person","http://Microsoft.ServiceModel.Samples");    
  public XmlNode[] Nodes  
  {  
    get {return this.nodesField;}  
    set {this.nodesField = value;}  
  }    
  public void ReadXml(XmlReader reader)  
  {  
    this.nodesField = XmlSerializableServices.ReadNodes(reader);  
  }    
  public void WriteXml(XmlWriter writer)  
  {  
    XmlSerializableServices.WriteNodes(writer, this.Nodes);  
  }    
  public System.Xml.Schema.XmlSchema GetSchema()  
  {  
    return null;  
  }    
  public static XmlQualifiedName ExportSchema(XmlSchemaSet schemas)  
  {  
    XmlSerializableServices.AddDefaultSchema(schemas, typeName);  
    return typeName;  
  }  
}  
```  
  
## <a name="datetimeoffset-serialization"></a><span data-ttu-id="5fb3e-494">DateTimeOffset - сериализация</span><span class="sxs-lookup"><span data-stu-id="5fb3e-494">DateTimeOffset Serialization</span></span>  
 <span data-ttu-id="5fb3e-495"><xref:System.DateTimeOffset> не обрабатывается как примитивный тип.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-495">The <xref:System.DateTimeOffset> is not treated as a primitive type.</span></span> <span data-ttu-id="5fb3e-496">Вместо этого он сериализуется как сложный элемент с двумя частями.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-496">Instead, it is serialized as a complex element with two parts.</span></span> <span data-ttu-id="5fb3e-497">Первая часть представляет дату и время, а вторая - смещение даты и времени.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-497">The first part represents the date time, and the second part represents the offset from the date time.</span></span> <span data-ttu-id="5fb3e-498">В следующем примере кода показано значение DateTimeOffset.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-498">An example of a serialized DateTimeOffset value is shown in the following code.</span></span>  
  
```xml  
<OffSet xmlns:a="http://schemas.datacontract.org/2004/07/System">  
  <DateTime i:type="b:dateTime" xmlns=""   
    xmlns:b="http://www.w3.org/2001/XMLSchema">2008-08-28T08:00:00    
  </DateTime>   
  <OffsetMinutes i:type="b:short" xmlns=""   
   xmlns:b="http://www.w3.org/2001/XMLSchema">-480  
   </OffsetMinutes>   
</OffSet>  
```  
  
 <span data-ttu-id="5fb3e-499">Схема выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5fb3e-499">The schema is as follows.</span></span>  
  
```xml  
<xs:schema targetNamespace="http://schemas.datacontract.org/2004/07/System">  
   <xs:complexType name="DateTimeOffset">  
      <xs:sequence minOccurs="1" maxOccurs="1">  
         <xs:element name="DateTime" type="xs:dateTime"  
         minOccurs="1" maxOccurs="1" />  
         <xs:element name="OffsetMinutes" type="xs:short"  
         minOccurs="1" maxOccurs="1" />  
      </xs:sequence>  
   </xs:complexType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5fb3e-500">См. также</span><span class="sxs-lookup"><span data-stu-id="5fb3e-500">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- [<span data-ttu-id="5fb3e-501">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="5fb3e-501">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
