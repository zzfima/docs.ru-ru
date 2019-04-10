---
title: Справочные сведения о взаимодействии объектов
ms.date: 03/30/2017
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: 9cbbd5a34269a7c4a5c33d72487a02df21f2f0fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222709"
---
# <a name="interoperable-object-references"></a><span data-ttu-id="2be11-102">Справочные сведения о взаимодействии объектов</span><span class="sxs-lookup"><span data-stu-id="2be11-102">Interoperable Object References</span></span>
<span data-ttu-id="2be11-103">По умолчанию <xref:System.Runtime.Serialization.DataContractSerializer> сериализует объекты по значению.</span><span class="sxs-lookup"><span data-stu-id="2be11-103">By default the <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="2be11-104">Можно использовать свойство <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>, чтобы сериализатор контракта данных сохранял ссылки на объекты во время сериализации объектов этого типа.</span><span class="sxs-lookup"><span data-stu-id="2be11-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the Data Contract Serializer to preserve object references when serializing objects of the type.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="2be11-105">Созданный идентификатор XML</span><span class="sxs-lookup"><span data-stu-id="2be11-105">Generated XML</span></span>  
 <span data-ttu-id="2be11-106">В качестве примера рассмотрим следующий объект:</span><span class="sxs-lookup"><span data-stu-id="2be11-106">As an example, consider the following object:</span></span>  
  
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
  
 <span data-ttu-id="2be11-107">Если <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> задано как `false` (по умолчанию), создается следующий код XML:</span><span class="sxs-lookup"><span data-stu-id="2be11-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="2be11-108">Если <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> задано как `true`, создается следующий код XML:</span><span class="sxs-lookup"><span data-stu-id="2be11-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1" />  
</X>  
```  
  
 <span data-ttu-id="2be11-109">Однако <xref:System.Runtime.Serialization.XsdDataContractExporter> не описывает атрибуты `id` и `ref` в этой схеме, даже если свойство `preserveObjectReferences` задано как `true`.</span><span class="sxs-lookup"><span data-stu-id="2be11-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> does not describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="2be11-110">Использование IsReference</span><span class="sxs-lookup"><span data-stu-id="2be11-110">Using IsReference</span></span>  
 <span data-ttu-id="2be11-111">Чтобы создать информацию о ссылке на объект, допустимую согласно схеме, которая ее описывает, примените атрибут <xref:System.Runtime.Serialization.DataContractAttribute> к типу и задайте флаг <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> как `true`.</span><span class="sxs-lookup"><span data-stu-id="2be11-111">To generate object reference information that is valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="2be11-112">Использование `IsReference` в предыдущем примере класса `X`:</span><span class="sxs-lookup"><span data-stu-id="2be11-112">Using `IsReference` in the previous example class `X`:</span></span>  
  
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
  
 <span data-ttu-id="2be11-113">Созданный код XML выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2be11-113">The generated XML is as follows:</span></span>  
  
 `<X>`  
  
 `<A id="1">`  
  
 `<Value>contents of A</Value>`  
  
 `</A>`  
  
 `<B ref="1">`  
  
 `</B>`  
  
 `</X>`  
  
 <span data-ttu-id="2be11-114">Использование `IsReference` обеспечивает совместимость для цикла обработки сообщений.</span><span class="sxs-lookup"><span data-stu-id="2be11-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="2be11-115">В противном случае при создании типа из схемы то, что отправляется обратно как XML для этого типа, может быть несовместимым с изначально предполагаемой схемой.</span><span class="sxs-lookup"><span data-stu-id="2be11-115">Without it, when a type is generated from schema, what is sent back as XML for that type is not necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="2be11-116">Другими словами, несмотря на сериализацию атрибутов `id` и `ref`, первоначальная схема могла предотвратить появление этих атрибутов (или всех атрибутов) в XML.</span><span class="sxs-lookup"><span data-stu-id="2be11-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="2be11-117">Когда `IsReference` применен к члену данных, во время передачи туда и обратно член по-прежнему распознается как член, на который можно дать ссылку.</span><span class="sxs-lookup"><span data-stu-id="2be11-117">With `IsReference` applied to a data member, the member continues to be recognized as "referenceable" when roundtripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be11-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2be11-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference%2A>
