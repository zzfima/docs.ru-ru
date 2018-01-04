---
title: "Справочные сведения о взаимодействии объектов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3d74c54d29f7da085d9d87bf37cc93078726f308
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="interoperable-object-references"></a><span data-ttu-id="b66e2-102">Справочные сведения о взаимодействии объектов</span><span class="sxs-lookup"><span data-stu-id="b66e2-102">Interoperable Object References</span></span>
<span data-ttu-id="b66e2-103">По умолчанию <xref:System.Runtime.Serialization.DataContractSerializer> сериализует объекты по значению.</span><span class="sxs-lookup"><span data-stu-id="b66e2-103">By default the <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="b66e2-104">Можно использовать свойство <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>, чтобы сериализатор контракта данных сохранял ссылки на объекты во время сериализации объектов этого типа.</span><span class="sxs-lookup"><span data-stu-id="b66e2-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the Data Contract Serializer to preserve object references when serializing objects of the type.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="b66e2-105">Созданный идентификатор XML</span><span class="sxs-lookup"><span data-stu-id="b66e2-105">Generated XML</span></span>  
 <span data-ttu-id="b66e2-106">В качестве примера рассмотрим следующий объект:</span><span class="sxs-lookup"><span data-stu-id="b66e2-106">As an example, consider the following object:</span></span>  
  
```  
[DataContract]  
public class X  
{  
    SomeClass someInstance = new SomeClass();  
    [DataMember]  
    public SomeClass A = someInstance;  
    [DataMember]  
    public SomeClass B = someInstance;  
}  
  
public class SomeClass   
{  
}  
```  
  
 <span data-ttu-id="b66e2-107">Если <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> задано как `false` (по умолчанию), создается следующий код XML:</span><span class="sxs-lookup"><span data-stu-id="b66e2-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="b66e2-108">Если <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> задано как `true`, создается следующий код XML:</span><span class="sxs-lookup"><span data-stu-id="b66e2-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1" />  
</X>  
```  
  
 <span data-ttu-id="b66e2-109">Однако <xref:System.Runtime.Serialization.XsdDataContractExporter> не описывает атрибуты `id` и `ref` в этой схеме, даже если свойство `preserveObjectReferences` задано как `true`.</span><span class="sxs-lookup"><span data-stu-id="b66e2-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> does not describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="b66e2-110">Использование IsReference</span><span class="sxs-lookup"><span data-stu-id="b66e2-110">Using IsReference</span></span>  
 <span data-ttu-id="b66e2-111">Чтобы создать информацию о ссылке на объект, допустимую согласно схеме, которая ее описывает, примените атрибут <xref:System.Runtime.Serialization.DataContractAttribute> к типу и задайте флаг <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> как `true`.</span><span class="sxs-lookup"><span data-stu-id="b66e2-111">To generate object reference information that is valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="b66e2-112">Использование `IsReference` в предыдущем примере класса `X`:</span><span class="sxs-lookup"><span data-stu-id="b66e2-112">Using `IsReference` in the previous example class `X`:</span></span>  
  
 `[DataContract(IsReference=true)] public class X`  
  
 `{`  
  
 `SomeClass someInstance = new SomeClass();`  
  
 `[DataMember]`  
  
 `public SomeClass A = someInstance;`  
  
 `[DataMember]`  
  
 `public SomeClass B = someInstance;`  
  
 `}`  
  
 `public class SomeClass`  
  
 `{`  
  
 `}`  
  
 <span data-ttu-id="b66e2-113">Созданный код XML выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b66e2-113">The generated XML is as follows:</span></span>  
  
 `<X>`  
  
 `<A id="1">`  
  
 `<Value>contents of A</Value>`  
  
 `</A>`  
  
 `<B ref="1">`  
  
 `</B>`  
  
 `</X>`  
  
 <span data-ttu-id="b66e2-114">Использование `IsReference` обеспечивает совместимость для цикла обработки сообщений.</span><span class="sxs-lookup"><span data-stu-id="b66e2-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="b66e2-115">В противном случае при создании типа из схемы то, что отправляется обратно как XML для этого типа, может быть несовместимым с изначально предполагаемой схемой.</span><span class="sxs-lookup"><span data-stu-id="b66e2-115">Without it, when a type is generated from schema, what is sent back as XML for that type is not necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="b66e2-116">Другими словами, несмотря на сериализацию атрибутов `id` и `ref`, первоначальная схема могла предотвратить появление этих атрибутов (или всех атрибутов) в XML.</span><span class="sxs-lookup"><span data-stu-id="b66e2-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="b66e2-117">Когда `IsReference` применен к члену данных, во время передачи туда и обратно член по-прежнему распознается как член, на который можно дать ссылку.</span><span class="sxs-lookup"><span data-stu-id="b66e2-117">With `IsReference` applied to a data member, the member continues to be recognized as "referenceable" when roundtripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b66e2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b66e2-118">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>  
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference%2A>
