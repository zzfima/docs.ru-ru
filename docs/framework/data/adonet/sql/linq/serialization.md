---
title: "Сериализация | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a15ae411-8dc2-4ca3-84d2-01c9d5f1972a
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Сериализация
В этом разделе рассматриваются возможности сериализации [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  В приведенных ниже подразделах приводятся сведения о добавлении сериализации в процессе создания кода во время разработки, а также о поведении классов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] при сериализации во время выполнения.  
  
 Код сериализации можно добавить во время разработки одним из перечисленных ниже методов.  
  
-   В конструкторе [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] установите для свойства **Режим сериализации** значение **в одном направлении**.  
  
-   В программе командной строки SQLMetal добавьте параметр **\/serialization**.  Дополнительные сведения см. в разделе [SqlMetal.exe \(средство создания кода\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## Обзор  
 Код, созданный с помощью [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], по умолчанию предоставляет возможности отложенной загрузки.  Отложенная загрузка \- очень удобное средство среднего уровня для прозрачной загрузки данных по требованию.  Однако при сериализации с этим средством возникают проблемы, поскольку сериализатор инициирует отложенную загрузку независимо от намерений пользователя.  В действительности, при сериализации объекта также сериализуется его транзитивное замыкание для всех исходящих ссылок с отложенной загрузкой.  
  
 Функция сериализации [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] устраняет эту проблему, в первую очередь, благодаря двум описанным далее механизмам.  
  
-   Режим <xref:System.Data.Linq.DataContext> для выключения отложенной загрузки \(<xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>\).  Для получения дополнительной информации см. <xref:System.Data.Linq.DataContext>.  
  
-   Переключение создания кода на создания атрибутов <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=fullName> и <xref:System.Runtime.Serialization.DataMemberAttribute?displayProperty=fullName> в создаваемых классах.  Главной темой этого раздела является именно этот аспект, включая поведение классов с отложенной загрузкой при сериализации.  
  
### Определения  
  
-   *Сериализатор DataContract*: используется по умолчанию компонентом Windows Communication Framework \(WCF\) на версии платформы .NET Framework 3.0 или выше.  
  
-   *Однонаправленная сериализация*: сериализованная версия класса, которая содержит только однонаправленное свойство ассоциации \(во избежание зацикливания\).  По соглашению, для сериализации помечается свойство родительской стороны отношения «первичный ключ \- внешний ключ».  Другая сторона, участвующая в двунаправленном отношении, не сериализуется.  
  
     Однонаправленная сериализация является единственным типом сериализации, поддерживаемым технологией [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
## Пример кода  
 В представленном ниже коде используются традиционные классы `Customer` и `Order` из учебной базы данных « Northwind" и демонстрируется, как добавить к этим классам атрибуты сериализации.  
  
 [!code-csharp[DLinqSerialization#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#1)]
 [!code-vb[DLinqSerialization#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#1)]  
  
 [!code-csharp[DLinqSerialization#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#2)]
 [!code-vb[DLinqSerialization#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#2)]  
  
 [!code-csharp[DLinqSerialization#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#3)]
 [!code-vb[DLinqSerialization#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#3)]  
  
 Для краткости в следующем примере для класса `Order` показано только обратное свойство отношения, соответствующее классу `Customer`.  Этот класс не имеет атрибута `DataMember`, чтобы избежать зацикливания.  
  
 [!code-csharp[DLinqSerialization#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#4)]
 [!code-vb[DLinqSerialization#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#4)]  
  
 [!code-csharp[DLinqSerialization#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#5)]
 [!code-vb[DLinqSerialization#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#5)]  
  
### Сериализация сущностей  
 Сущности в коде, показанном в предыдущих примерах, можно сериализовать следующим образом:  
  
 [!code-csharp[DLinqSerialization#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/Program.cs#6)]
 [!code-vb[DLinqSerialization#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/Module1.vb#6)]  
  
### Саморекурсивные отношения  
 Саморекурсивные отношения следуют тому же шаблону.  Свойство отношения, соответствующее внешнему ключу, не имеет атрибута `DataMember`, в то время как родительское свойство этот атрибут имеет.  
  
 Рассмотрим следующий класс, содержащий две саморекурсивные связи: Employee.Manager\/Reports и Employee.Mentor\/Mentees.  
  
 [!code-csharp[DLinqSerialization#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#7)]
 [!code-vb[DLinqSerialization#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#7)]  
  
## См. также  
 [Дополнительные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)   
 [SqlMetal.exe \(средство создания кода\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)   
 [Как обеспечить сериализацию сущностей](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)