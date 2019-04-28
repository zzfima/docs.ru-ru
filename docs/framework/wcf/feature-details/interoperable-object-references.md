---
title: Ссылки на сведения о взаимодействии объектов
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: ada9084f6ac3c97dc641571c0cb8379a2fac68a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918974"
---
# <a name="interoperable-object-references"></a><span data-ttu-id="e818a-102">Ссылки на сведения о взаимодействии объектов</span><span class="sxs-lookup"><span data-stu-id="e818a-102">Interoperable object references</span></span>
<span data-ttu-id="e818a-103">По умолчанию <xref:System.Runtime.Serialization.DataContractSerializer> сериализует объекты по значению.</span><span class="sxs-lookup"><span data-stu-id="e818a-103">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="e818a-104">Можно использовать <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> свойство, чтобы сериализатор контракта данных сохранял ссылки на объекты при сериализации объектов.</span><span class="sxs-lookup"><span data-stu-id="e818a-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="e818a-105">Созданный идентификатор XML</span><span class="sxs-lookup"><span data-stu-id="e818a-105">Generated XML</span></span>  
 <span data-ttu-id="e818a-106">В качестве примера рассмотрим следующий объект:</span><span class="sxs-lookup"><span data-stu-id="e818a-106">As an example, consider the following object:</span></span>  
  
```csharp  
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
  
 <span data-ttu-id="e818a-107">Если <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> задано как `false` (по умолчанию), создается следующий код XML:</span><span class="sxs-lookup"><span data-stu-id="e818a-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="e818a-108">Если <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> задано как `true`, создается следующий код XML:</span><span class="sxs-lookup"><span data-stu-id="e818a-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="e818a-109">Тем не менее <xref:System.Runtime.Serialization.XsdDataContractExporter> не приведено `id` и `ref` атрибутов в этой схеме, даже если `preserveObjectReferences` свойству `true`.</span><span class="sxs-lookup"><span data-stu-id="e818a-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="e818a-110">Использование IsReference</span><span class="sxs-lookup"><span data-stu-id="e818a-110">Using IsReference</span></span>  
 <span data-ttu-id="e818a-111">Чтобы создать объект справочные сведения, который является допустимым в соответствии со схемой, которая ее описывает, примените <xref:System.Runtime.Serialization.DataContractAttribute> к типу атрибут и задать <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> флаг `true`.</span><span class="sxs-lookup"><span data-stu-id="e818a-111">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="e818a-112">В следующем примере изменяется класс `X` в предыдущем примере, добавив `IsReference`:</span><span class="sxs-lookup"><span data-stu-id="e818a-112">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
```csharp
[DataContract(IsReference=true)]
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
````

 <span data-ttu-id="e818a-113">Созданный код XML выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e818a-113">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A> 
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="e818a-114">Использование `IsReference` обеспечивает совместимость для цикла обработки сообщений.</span><span class="sxs-lookup"><span data-stu-id="e818a-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="e818a-115">Без него при генерации типа из схемы XML выходных данных для что тип не быть несовместимым с изначально предполагаемой схемой.</span><span class="sxs-lookup"><span data-stu-id="e818a-115">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="e818a-116">Другими словами, несмотря на сериализацию атрибутов `id` и `ref`, первоначальная схема могла предотвратить появление этих атрибутов (или всех атрибутов) в XML.</span><span class="sxs-lookup"><span data-stu-id="e818a-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="e818a-117">С помощью `IsReference` применяется к члену данных, член по-прежнему распознается как *referenceable* при обхода.</span><span class="sxs-lookup"><span data-stu-id="e818a-117">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e818a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e818a-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
