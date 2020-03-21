---
title: Совместимые ссылки на объекты
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: 0927f217a1666f8f27ca9c3e68f80a96b9c0f2b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184708"
---
# <a name="interoperable-object-references"></a>Совместимые ссылки на объекты
По умолчанию <xref:System.Runtime.Serialization.DataContractSerializer> сериализуем объекты по стоимости. Свойство <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> может использовать для инструктажа сериализатора контракта данных для сохранения ссылок на объекты при сериализации объектов.  
  
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
  
 Тем <xref:System.Runtime.Serialization.XsdDataContractExporter> не менее, `id` не `ref` описывает и атрибуты в своей схеме, даже если `preserveObjectReferences` свойство настроено на `true`.  
  
## <a name="using-isreference"></a>Использование IsReference  
 Для создания справочной информации объекта, которая действительна в <xref:System.Runtime.Serialization.DataContractAttribute> соответствии с описанной <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> схемой, примените атрибут к типу и установите флаг. `true` Следующий пример изменяет класс `X` в `IsReference`предыдущем примере, добавляя:  
  
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
  
 Использование `IsReference` обеспечивает совместимость для цикла обработки сообщений. Без этого, когда тип генерируется из схемы, выход XML для этого типа не обязательно совместим с первоначально предполагаемой схемой. Другими словами, несмотря на сериализацию атрибутов `id` и `ref`, первоначальная схема могла предотвратить появление этих атрибутов (или всех атрибутов) в XML. При `IsReference` применении к участнику данных участник по-прежнему признается в качестве *ориентируемого* при круглом опере.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
