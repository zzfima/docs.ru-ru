---
title: "Как сопоставить связи базы данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Как сопоставить связи базы данных
Отношения данных, которые всегда останутся неизменными, можно закодировать в виде ссылок в классе сущностей.  В учебной базе данных Northwind, всегда существует связь между заказчиками и их заказами, т.к. обычно заказчики размещают заказы.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определяет атрибут <xref:System.Data.Linq.Mapping.AssociationAttribute>, с помощью которого представляются такие отношения.  Этот атрибут используется совместно с типами <xref:System.Data.Linq.EntitySet%601> и <xref:System.Data.Linq.EntityRef%601> для представления в базе данных связи по внешнему ключу. Дополнительные сведения см. в разделе «Атрибут Association» статьи [Сопоставление на основе атрибутов](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
> [!NOTE]
>  В значениях свойства Storage для атрибутов AssociationAttribute и ColumnAttribute учитывается регистр.  Например, следует убедиться в том, что регистр символов в значении, использованном в атрибуте свойства AssociationAttribute.Storage, соответствует регистру символов в соответствующих именах свойств в остальном коде.  Это относится ко всем языкам программирования среды .NET, даже к тем, которые обычно не учитывают регистр, включая [!INCLUDE[vb_current_short](../../../../../../includes/vb-current-short-md.md)].  Дополнительные сведения о свойстве Storage см. в разделе <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=fullName>.  
  
 Большинство связей имеют тип «один ко многим», как и в примере, представленном далее в этом разделе.  Отношения "один\-к\-одному" и "один\-ко\-многим" можно представить следующим образом.  
  
-   Один к одному. Этот тип связей представляется включением элементов <xref:System.Data.Linq.EntitySet%601> с обеих сторон.  
  
     Например, рассмотрим отношение `Customer`\-`SecurityCode`, созданное таким образом, что код безопасности клиента не будет найден в таблице `Customer`, а может быть получен только авторизованными лицами.  
  
-   Многие ко многим. В связях типа «многие ко многим» первичный ключ связанной таблицы \(называемой также таблицей *соединения*\) часто формируется составлением внешних ключей из двух других таблиц.  
  
     В качестве примера рассмотрим связь `Employee`\-`Project` типа «многие ко многим», образованную с помощью связанной таблицы `EmployeeProject`.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] требует, чтобы такая связь моделировалась по трем классам: `Employee`, `Project` и `EmployeeProject`.  В этом случае изменение отношения между `Employee` и `Project` может потребовать обновления первичного ключа `EmployeeProject`.  Однако данная ситуация наилучшим образом моделируется для удаления существующего `EmployeeProject` и создания нового `EmployeeProject`.  
  
    > [!NOTE]
    >  Отношения в реляционных базах данных обычно моделируются в виде значений внешнего ключа, ссылающихся на первичные ключи в других таблицах.  Для перемещения между ними следует явно связать две таблицы с помощью реляционной операции *соединения*.  
    >   
    >  С другой стороны, объекты в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ссылаются друг на друга с помощью ссылок свойств или коллекций ссылок, к которым можно перейти с использованием *точечной* нотации.  
  
## Пример  
 В следующем примере отношения "один\-ко\-многим" класс `Customer` имеет свойство, объявляющее отношение между клиентами и их заказами.  Свойство `Orders` имеет тип <xref:System.Data.Linq.EntitySet%601>.  Этот тип указывает, что данное отношение относится к виду "один\-ко\-многим" \(один клиент \- много заказов\).  Свойство <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A> используется для описания установки данной связи, а именно: путем указания в связанном классе имени свойства, которое будет сравниваться с существующим.  В этом примере свойство `CustomerID` сравнивается таким образом, как если бы *соединение* базы данных сравнивалось с данным значением столбца.  
  
> [!NOTE]
>  Если разработка производится в среде [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], то можно воспользоваться [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для создания ассоциации между классами.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## Пример  
 Возможна и обратная ситуация.  Для описания ассоциации между клиентами и заказами вместо класса `Customer` можно использовать класс `Order`.  Чтобы описать обратную связь с клиентом, класс `Order` использует тип <xref:System.Data.Linq.EntityRef%601>, как показано в следующем примере кода.  
  
> [!NOTE]
>  Класс <xref:System.Data.Linq.EntityRef%601> поддерживает *отложенную загрузку*.  Дополнительные сведения  *см. в разделе* [Сравнение отложенной и немедленной загрузки](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## См. также  
 [Как настроить классы сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)   
 [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)