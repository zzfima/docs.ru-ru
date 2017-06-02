---
title: "Модель объектов LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 81dd0c37-e2a4-4694-83b0-f2e49e693810
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Модель объектов LINQ to SQL
В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объектная модель, выраженная на языке программирования разработчика, сопоставляется модели данных реляционной базы данных.  После этого операции с данными выполняются в соответствии с объектной моделью.  
  
 В данном сценарии команды базы данных \(например, `INSERT`\) не выполняются в базе данных.  Вместо этого изменение значений и выполнение методов происходит в рамках объектной модели.  Если необходимо отправить запрос к базе данных или передать изменения, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует требования в корректные команды SQL и отправляет эти команды в базу данных.  
  
 ![DLinqObjectModel](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinqobjectmodel.png "DLinqObjectModel")  
  
 В следующей таблице представлены самые основные элементы в объектной модели [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и их связь с элементами в реляционной модели данных.  
  
|Объектная модель LINQ to SQL|Реляционная модель данных|  
|----------------------------------|-------------------------------|  
|Класс сущностей|Таблица|  
|Член класса|Столбец|  
|Ассоциация|Отношение внешнего ключа|  
|Метод|Хранимая процедура или функция|  
  
> [!NOTE]
>  Следующие сведения подразумевают наличие базовых знаний о реляционной модели данных и правилах.  
  
## Таблицы классов сущностей и баз данных LINQ to SQL  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] таблица базы данных представлена *классом сущностей*.  Класс сущностей аналогичен любому другому создаваемому классу за исключением того, что для снабжения класса примечаниями используются специальные данные, связывающие его с таблицей базы данных.  Для этого к объявлению класса добавляется пользовательский атрибут \(<xref:System.Data.Linq.Mapping.TableAttribute>\), как показано в следующем примере.  
  
### Пример  
 [!code-csharp[DLinqObjectModel#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#1)]
 [!code-vb[DLinqObjectModel#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#1)]  
  
 В базе данных могут быть сохранены только экземпляры классов, объявленные как таблицы \(то есть классы сущностей\).  
  
 Дополнительные сведения см. в разделе «Атрибут Table» статьи [Сопоставление на основе атрибутов](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## Столбцы членов класса и базы данных LINQ to SQL  
 Кроме связывания классов с таблицами, можно назначить поля или свойства для представления столбцов базы данных.  Для этого [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определяет атрибут <xref:System.Data.Linq.Mapping.ColumnAttribute>, как показано в следующем примере.  
  
### Пример  
 [!code-csharp[DLinqObjectModel#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#2)]
 [!code-vb[DLinqObjectModel#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#2)]  
  
 В базе данных сохраняются или из нее извлекаются только те поля и свойства, которые сопоставлены столбцам.  Поля и свойства, не объявленные в качестве столбцов, считаются временными частями логики приложения.  
  
 Атрибут <xref:System.Data.Linq.Mapping.ColumnAttribute> имеет целый ряд свойств, которые можно использовать для настройки членов, представляющих столбцы \(например, назначение члена, представляющего столбец первичного ключа\).  Дополнительные сведения см. в разделе «Атрибут Column» статьи [Сопоставление на основе атрибутов](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## Связи и отношения внешнего ключа баз данных LINQ to SQL  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для представления связей базы данных \(например, отношений между первичным и внешним ключами\) используется атрибут <xref:System.Data.Linq.Mapping.AssociationAttribute>.  В следующем сегменте кода класс `Order` содержит свойство возвращается свойство `Customer`, имеющее атрибут <xref:System.Data.Linq.Mapping.AssociationAttribute>.  Это свойство и его атрибут предоставляют класс `Order` с отношением для класса `Customer`.  
  
 В следующем примере кода представлено свойство `Customer` из класса `Order`.  
  
### Пример  
 [!code-csharp[DLinqObjectModel#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#3)]
 [!code-vb[DLinqObjectModel#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#3)]  
  
 Дополнительные сведения см. в разделе «Атрибут Association» статьи [Сопоставление на основе атрибутов](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## Хранимые процедуры методов и баз данных LINQ to SQL.  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает хранимые процедуры и пользовательские функции.  В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] эти абстракции, определенные базой данных, сопоставляются с клиентскими объектами так, что к ним можно обращаться из клиентского кода в режиме строгой типизации.  Подписи методов очень схожи с сигнатурами процедур и функций, определенных в базе данных.  Для определения этих методов можно использовать IntelliSense.  
  
 В качестве набора результатов, возвращенного вызовом сопоставленной процедуры, выступает строго типизированная коллекция.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сопоставляет хранимые процедуры и функции с методами с помощью атрибутов <xref:System.Data.Linq.Mapping.FunctionAttribute> и <xref:System.Data.Linq.Mapping.ParameterAttribute>.  Методы, представляющие хранимые процедуры, отличаются от методов, представляющих пользовательские функции, свойством <xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A>.  Если данное свойство имеет значение `false` \(значение по умолчанию\), значит метод представляет хранимую процедуру.  Если свойству задано значение `true`, метод представляет функцию базы данных.  
  
> [!NOTE]
>  Пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] могут воспользоваться конструктором [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для создания методов, сопоставленных с хранимыми процедурами и определяемыми пользователем функциями.  
  
### Пример  
 [!code-csharp[DLinqObjectModel#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#4)]
 [!code-vb[DLinqObjectModel#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#4)]  
  
 Дополнительные сведения см. в описаниях атрибутов Function, Stored Procedure и Parameter в разделах [Сопоставление на основе атрибутов](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md) и [Хранимые процедуры](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).  
  
## См. также  
 [Сопоставление на основе атрибутов](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)   
 [Дополнительные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)