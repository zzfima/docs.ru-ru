---
title: Известные типы контрактов данных
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], known types
- KnownTypeAttribute [WCF]
- KnownTypes [WCF]
ms.assetid: 1a0baea1-27b7-470d-9136-5bbad86c4337
caps.latest.revision: 42
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c9c180a0f1544fa187ddb53ec79a47f908c298d7
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="data-contract-known-types"></a>Известные типы контрактов данных
Класс <xref:System.Runtime.Serialization.KnownTypeAttribute> позволяет заранее задавать типы, которые следует рассматривать при десериализации. Рабочий пример см. в разделе [Known Types](../../../../docs/framework/wcf/samples/known-types.md) .  
  
 Обычно при передаче параметров и возвращаемых значений между клиентом и службой обе конечные точки совместно используют все контракты данных, относящиеся к передаваемым данным. Однако в следующих ситуациях это не так:  
  
-   Контракт отправляемых данных унаследован из контракта ожидаемых данных. Дополнительные сведения см. в разделе о наследования в [эквивалентность контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)). В этом случае контракт передаваемых данных отличается от контракта данных, ожидаемого принимающей конечной точкой;  
  
-   объявленный тип передаваемых данных является интерфейсом, а не классом, структурой или перечислением. Поэтому невозможно заранее знать, какой именно из реализуемых этим интерфейсом типов будет передан, а следовательно принимающая конечная точка не может заранее определить контракт передаваемых данных;  
  
-   объявлен тип передаваемых данных <xref:System.Object>. Поскольку каждый тип наследуется от класса <xref:System.Object>, невозможно заранее знать, какой именно тип будет передан, а следовательно принимающая конечная точка не может заранее определить контракт передаваемых данных. Это частный случай первого варианта: каждый контракт данных наследует от контракта данных по умолчанию (пустого контракта), который создается для класса <xref:System.Object>;  
  
-   у некоторых типов, включающих типы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] , имеются члены, относящиеся к одной из указанных выше трех категорий. Например, класс <xref:System.Collections.Hashtable> использует класс <xref:System.Object> для хранения фактических объектов в хэш-таблице. При сериализации таких типов принимающая сторона не может заранее определить контракт данных таких членов.  
  
## <a name="the-knowntypeattribute-class"></a>Класс KnownTypeAttribute  
 Когда данные прибывают в принимающую конечную точку, среда выполнения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предпринимает попытку десериализовать данные в экземпляр типа среды CLR. Тип, экземпляр которого создается в результате десериализации, выбирается в первую очередь по результатам проверки входящего сообщения с целью определения контракта данных, которому соответствует содержимое сообщения. После этого система десериализации пытается найти тип среды CLR, который реализует контракт данных, совместимый с содержимым сообщения. Набор потенциальных типов, которые система десериализации считает допустимыми в результате выполнения этих операций, называется набором "известных типов" десериализатора.  
  
 Один из способов уведомления десериализатора о типе - использовать класс <xref:System.Runtime.Serialization.KnownTypeAttribute>. Этот атрибут нельзя применять к отдельным членам, но следует применять только к целым типам контрактов данных. Атрибут применяется к *внешнему типу* , который может быть классом или структурой. На самом базовом уровне применение этого атрибута помечает тип в качестве "известного типа". В результате известный тип становится частью набора известных типов всякий раз, когда происходит десериализация объекта внешнего типа или любого объекта, являющегося членом известного типа. К одному и тому же типу можно применить несколько атрибутов <xref:System.Runtime.Serialization.KnownTypeAttribute> .  
  
## <a name="known-types-and-primitives"></a>Известные типы и примитивы  
 Типы-примитивы, а также некоторые типы, с которыми обращаются как с примитивами (например, <xref:System.DateTime> и <xref:System.Xml.XmlElement>), всегда являются "известными", и их никогда не нужно добавлять с помощью описанного механизма. Однако массивы типов-примитивов нужно добавлять в явном виде. Большинство коллекций считаются эквивалентами массивов. (Неуниверсальные коллекции считаются эквивалентами массивов <xref:System.Object>.) Пример использования примитивов, массивов примитивов и коллекций примитивов см. в примере 4.  
  
> [!NOTE]
>  В отличие от других типов-примитивов структура <xref:System.DateTimeOffset> по умолчанию не является известным типом, поэтому ее необходимо вручную добавлять в список известных типов.  
  
## <a name="examples"></a>Примеры  
 Ниже приведены примеры использования класса <xref:System.Runtime.Serialization.KnownTypeAttribute> .  
  
#### <a name="example-1"></a>Пример 1  
 Имеется три класса, связанных отношениями наследования.  
  
 [!code-csharp[C_KnownTypeAttribute#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#1)]
 [!code-vb[C_KnownTypeAttribute#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#1)]  
  
 Показанный ниже класс `CompanyLogo` можно сериализовать; однако он не может быть сериализован, если член `ShapeOfLogo` имеет значение `CircleType` или `TriangleType` , поскольку система десериализации не распознает типы с именами контрактов данных "Circle" и "Triangle".  
  
 [!code-csharp[C_KnownTypeAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#2)]
 [!code-vb[C_KnownTypeAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#2)]  
  
 В следующем примере кода показано, как правильно описать тип `CompanyLogo` .  
  
 [!code-csharp[C_KnownTypeAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#3)]
 [!code-vb[C_KnownTypeAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#3)]  
  
 Когда происходит десериализация внешнего типа `CompanyLogo2` , система десериализации знает о типах `CircleType` и `TriangleType` и поэтому может найти контракты данных, соответствующие типам "Circle" и "Triangle".  
  
#### <a name="example-2"></a>Пример 2  
 В следующем примере, даже если оба типа `CustomerTypeA` и `CustomerTypeB` имеют контракт данных `Customer` , при десериализации типа `CustomerTypeB` будет создаваться экземпляр `PurchaseOrder` , поскольку системе десериализации известен только тип `CustomerTypeB` .  
  
 [!code-csharp[C_KnownTypeAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#4)]
 [!code-vb[C_KnownTypeAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#4)]  
  
#### <a name="example-3"></a>Пример 3  
 В следующем примере тип <xref:System.Collections.Hashtable> хранит содержимое в виде <xref:System.Object>. Для десериализации хэш-таблицы системе десериализации должен быть известен набор возможных типов, которые представляются этим типом. В данном случае нам известно, что в объекте `Book` хранятся только объекты `Magazine` и `Catalog`, поэтому они добавляются с помощью атрибута <xref:System.Runtime.Serialization.KnownTypeAttribute> .  
  
 [!code-csharp[C_KnownTypeAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#5)]
 [!code-vb[C_KnownTypeAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#5)]  
  
#### <a name="example-4"></a>Пример 4  
 В следующем примере контракт данных хранит число и операцию, которую следует выполнить над этим числом. Член данных `Numbers` может быть целым числом, массивом целых чисел или объектом <xref:System.Collections.Generic.List%601> , содержащим целые числа.  
  
> [!CAUTION]
>  Работает только на стороне клиента, если SVCUTIL.EXE используется для формирования учетной записи-посредника WCF. SVCUTIL.EXE извлекает метаданные из службы, включая любые известные типы. Без этой информации клиент не сможет десериализовать типы.  
  
 [!code-csharp[C_KnownTypeAttribute#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#6)]
 [!code-vb[C_KnownTypeAttribute#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#6)]  
  
 Ниже показан код приложения.  
  
 [!code-csharp[C_KnownTypeAttribute#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#7)]
 [!code-vb[C_KnownTypeAttribute#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#7)]  
  
## <a name="known-types-inheritance-and-interfaces"></a>Известные типы, наследование и интерфейсы  
 Когда известный тип связывается с конкретным типом с помощью атрибута `KnownTypeAttribute` , он также связывается со всеми производными типами этого типа. См., например, следующий код.  
  
 [!code-csharp[C_KnownTypeAttribute#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#8)]
 [!code-vb[C_KnownTypeAttribute#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#8)]  
  
 Класс `DoubleDrawing` не требует, чтобы атрибут `KnownTypeAttribute` использовал типы `Square` и `Circle` в поле `AdditionalShape` , поскольку эти атрибуты уже применены в базовом классе (`Drawing`).  
  
 Известные типы можно связывать только с классами и структурами, но не с интерфейсами.  
  
## <a name="known-types-using-open-generic-methods"></a>Известные типы и открытые универсальные методы  
 Может возникнуть необходимость добавить в качестве известного типа универсальный тип. Однако открытый универсальный тип невозможно передать в атрибут `KnownTypeAttribute` в качестве параметра.  
  
 Эту проблему можно решить с помощью альтернативного механизма: напишите метод, возвращающий типы, которые следует добавить в коллекцию известных типов. После этого имя метода задается в качестве строкового аргумента атрибута `KnownTypeAttribute` с некоторыми ограничениями.  
  
 Этот метод должен существовать в типе, к которому применяется атрибут `KnownTypeAttribute` , должен быть статическим, не должен принимать параметров и должен возвращать объект, который можно присвоить интерфейсу <xref:System.Collections.IEnumerable> типа <xref:System.Type>.  
  
 Нельзя объединять атрибут `KnownTypeAttribute` с именем метода и атрибутами `KnownTypeAttribute` с реальными типами в рамках одного типа. Более того, нельзя применять более одного атрибута `KnownTypeAttribute` с именем метода к одному и тому же типу.  
  
 См. приведенный ниже класс.  
  
 [!code-csharp[C_KnownTypeAttribute#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#9)]
 [!code-vb[C_KnownTypeAttribute#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#9)]  
  
 Поле `theDrawing` содержит экземпляры универсального класса `ColorDrawing` и универсального класса `BlackAndWhiteDrawing`, которые оба наследуют универсальному классу `Drawing`. В список известных типов должны быть добавлены оба типа, но следующий синтаксис является недопустимым для атрибутов.  
  
```csharp  
// Invalid syntax for attributes:  
// [KnownType(typeof(ColorDrawing<T>))]  
// [KnownType(typeof(BlackAndWhiteDrawing<T>))]  
```  
  
```vb  
' Invalid syntax for attributes:  
' <KnownType(GetType(ColorDrawing(Of T))), _  
' KnownType(GetType(BlackAndWhiteDrawing(Of T)))>  
```  
  
 Поэтому необходимо создать метод, который бы возвращал эти типы. В следующем примере кода показано, как правильно описать этот тип.  
  
 [!code-csharp[C_KnownTypeAttribute#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#10)]
 [!code-vb[C_KnownTypeAttribute#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#10)]  
  
## <a name="additional-ways-to-add-known-types"></a>Дополнительные способы добавления известных типов  
 Кроме того, известные типы можно добавлять с помощью файла конфигурации. Это бывает удобно, если нет возможности управлять типом, требующим для правильной сериализации применения списка известных типов, например при использовании в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]сторонних библиотек.  
  
 В следующем файле конфигурации показано, как задать известный тип в файле конфигурации.  
  
 `<configuration>`  
  
 `<system.runtime.serialization>`  
  
 `<dataContractSerializer>`  
  
 `<declaredTypes>`  
  
 `<add type="MyCompany.Library.Shape,`  
  
 `MyAssembly, Version=2.0.0.0, Culture=neutral,`  
  
 `PublicKeyToken=XXXXXX, processorArchitecture=MSIL">`  
  
 `<knownType type="MyCompany.Library.Circle,`  
  
 `MyAssembly, Version=2.0.0.0, Culture=neutral,`  
  
 `PublicKeyToken=XXXXXX, processorArchitecture=MSIL"/>`  
  
 `</add>`  
  
 `</declaredTypes>`  
  
 `</dataContractSerializer>`  
  
 `</system.runtime.serialization>`  
  
 `</configuration>`  
  
 В приведенном выше файле конфигурации объявлено, что тип контракта данных `MyCompany.Library.Shape` должен содержать известный тип `MyCompany.Library.Circle` .  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.KnownTypeAttribute>  
 <xref:System.Collections.Hashtable>  
 <xref:System.Object>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A>  
 [Известные типы](../../../../docs/framework/wcf/samples/known-types.md)  
 [Эквивалентность контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)  
 [Разработка контрактов службы](../../../../docs/framework/wcf/designing-service-contracts.md)
