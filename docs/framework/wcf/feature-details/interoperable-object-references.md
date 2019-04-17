---
title: Ссылки на сведения о взаимодействии объектов
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: ada9084f6ac3c97dc641571c0cb8379a2fac68a8
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59610643"
---
# <a name="interoperable-object-references"></a>Ссылки на сведения о взаимодействии объектов
По умолчанию <xref:System.Runtime.Serialization.DataContractSerializer> сериализует объекты по значению. Можно использовать <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> свойство, чтобы сериализатор контракта данных сохранял ссылки на объекты при сериализации объектов.  
  
## <a name="generated-xml"></a>Созданный идентификатор XML  
 В качестве примера рассмотрим следующий объект:  
  
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
  
 Если <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> задано как `false` (по умолчанию), создается следующий код XML:  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 Если <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> задано как `true`, создается следующий код XML:  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 Тем не менее <xref:System.Runtime.Serialization.XsdDataContractExporter> не приведено `id` и `ref` атрибутов в этой схеме, даже если `preserveObjectReferences` свойству `true`.  
  
## <a name="using-isreference"></a>Использование IsReference  
 Чтобы создать объект справочные сведения, который является допустимым в соответствии со схемой, которая ее описывает, примените <xref:System.Runtime.Serialization.DataContractAttribute> к типу атрибут и задать <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> флаг `true`. В следующем примере изменяется класс `X` в предыдущем примере, добавив `IsReference`:  
  
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

 Созданный код XML выглядит следующим образом:  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A> 
    <B ref="1"></B>  
</X>
```  
  
 Использование `IsReference` обеспечивает совместимость для цикла обработки сообщений. Без него при генерации типа из схемы XML выходных данных для что тип не быть несовместимым с изначально предполагаемой схемой. Другими словами, несмотря на сериализацию атрибутов `id` и `ref`, первоначальная схема могла предотвратить появление этих атрибутов (или всех атрибутов) в XML. С помощью `IsReference` применяется к члену данных, член по-прежнему распознается как *referenceable* при обхода.  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
