---
title: "Справочные сведения о взаимодействии объектов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Справочные сведения о взаимодействии объектов
По умолчанию <xref:System.Runtime.Serialization.DataContractSerializer> сериализует объекты по значению.  Можно использовать свойство <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>, чтобы сериализатор контракта данных сохранял ссылки на объекты во время сериализации объектов этого типа.  
  
## Созданный идентификатор XML  
 В качестве примера рассмотрим следующий объект:  
  
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
  
 Если <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> задано как `false` \(по умолчанию\), создается следующий код XML:  
  
```  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 Если <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> задано как `true`, создается следующий код XML:  
  
```  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1" />  
</X>  
```  
  
 Однако <xref:System.Runtime.Serialization.XsdDataContractExporter> не описывает атрибуты `id` и `ref` в этой схеме, даже если свойство `preserveObjectReferences` задано как `true`.  
  
## Использование IsReference  
 Чтобы создать информацию о ссылке на объект, допустимую согласно схеме, которая ее описывает, примените атрибут <xref:System.Runtime.Serialization.DataContractAttribute> к типу и задайте флаг <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> как `true`.  Использование `IsReference` в предыдущем примере класса `X`:  
  
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
  
 Созданный код XML выглядит следующим образом:  
  
 `<X>`  
  
 `<A id="1">`  
  
 `<Value>contents of A</Value>`  
  
 `</A>`  
  
 `<B ref="1">`  
  
 `</B>`  
  
 `</X>`  
  
 Использование `IsReference` обеспечивает совместимость для цикла обработки сообщений.  В противном случае при создании типа из схемы то, что отправляется обратно как XML для этого типа, может быть несовместимым с изначально предполагаемой схемой.  Другими словами, несмотря на сериализацию атрибутов `id` и `ref`, первоначальная схема могла предотвратить появление этих атрибутов \(или всех атрибутов\) в XML.  Когда `IsReference` применен к члену данных, во время передачи туда и обратно член по\-прежнему распознается как член, на который можно дать ссылку.  
  
## См. также  
 <xref:System.Runtime.Serialization.DataContractAttribute>   
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute>   
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>   
 <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference%2A>