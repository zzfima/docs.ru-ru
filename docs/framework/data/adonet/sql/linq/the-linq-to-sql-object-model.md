---
title: Модель объектов LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 81dd0c37-e2a4-4694-83b0-f2e49e693810
ms.openlocfilehash: 7ce759de004d479f5162d2ce3a965f5c40afa450
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110797"
---
# <a name="the-linq-to-sql-object-model"></a>Модель объектов LINQ to SQL
В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], в модель данных реляционной базы данных сопоставляется объектной модели, выраженной на языке программирования разработчика. После этого операции с данными выполняются в соответствии с объектной моделью.  
  
 В данном сценарии команды базы данных (например, `INSERT`) не выполняются в базе данных. Вместо этого изменение значений и выполнение методов происходит в рамках объектной модели. Если необходимо отправить запрос к базе данных или передать изменения, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует требования в корректные команды SQL и отправляет эти команды в базу данных.  
  
 ![DLinqObjectModel](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinqobjectmodel.png "DLinqObjectModel")  
  
 Самые основные элементы в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объектной модели и их связь с элементами в реляционной модели данных приведены в следующей таблице:  
  
|Объектная модель LINQ to SQL|Реляционная модель данных|  
|------------------------------|---------------------------|  
|Класс сущностей|Таблица|  
|Член класса|Столбец|  
|Ассоциация|Отношение внешнего ключа|  
|Метод|Хранимая процедура или функция|  
  
> [!NOTE]
>  Следующие сведения подразумевают наличие базовых знаний о реляционной модели данных и правилах.  
  
## <a name="linq-to-sql-entity-classes-and-database-tables"></a>Таблицы классов сущностей и баз данных LINQ to SQL  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], таблица базы данных представлена *класс сущностей*. Класс сущностей аналогичен любому другому создаваемому классу за исключением того, что для снабжения класса примечаниями используются специальные данные, связывающие его с таблицей базы данных. Для этого к объявлению класса добавляется пользовательский атрибут (<xref:System.Data.Linq.Mapping.TableAttribute>), как показано в следующем примере.  
  
### <a name="example"></a>Пример  
 [!code-csharp[DLinqObjectModel#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#1)]
 [!code-vb[DLinqObjectModel#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#1)]  
  
 В базе данных могут быть сохранены только экземпляры классов, объявленные как таблицы (то есть классы сущностей).  
  
 Дополнительные сведения см. в разделе атрибут Table [сопоставление, основанное на атрибутах](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## <a name="linq-to-sql-class-members-and-database-columns"></a>Столбцы членов класса и базы данных LINQ to SQL  
 Кроме связывания классов с таблицами, можно назначить поля или свойства для представления столбцов базы данных. Для этого [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определяет атрибут <xref:System.Data.Linq.Mapping.ColumnAttribute>, как показано в следующем примере.  
  
### <a name="example"></a>Пример  
 [!code-csharp[DLinqObjectModel#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#2)]
 [!code-vb[DLinqObjectModel#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#2)]  
  
 В базе данных сохраняются или из нее извлекаются только те поля и свойства, которые сопоставлены столбцам. Поля и свойства, не объявленные в качестве столбцов, считаются временными частями логики приложения.  
  
 Атрибут <xref:System.Data.Linq.Mapping.ColumnAttribute> имеет целый ряд свойств, которые можно использовать для настройки членов, представляющих столбцы (например, назначение члена, представляющего столбец первичного ключа). Дополнительные сведения см. в разделе атрибут столбца [сопоставление, основанное на атрибутах](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## <a name="linq-to-sql-associations-and-database-foreign-key-relationships"></a>Связи и отношения внешнего ключа баз данных LINQ to SQL  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], вы представления связей базы данных (например, внешнего ключа связи первичного ключа), применив <xref:System.Data.Linq.Mapping.AssociationAttribute> атрибута. В следующем фрагменте кода `Order` класс содержит `Customer` свойство, имеющее <xref:System.Data.Linq.Mapping.AssociationAttribute> атрибута. Это свойство и его атрибут предоставляют класс `Order` с отношением для класса `Customer`.  
  
 В следующем примере кода представлено свойство `Customer` из класса `Order`.  
  
### <a name="example"></a>Пример  
 [!code-csharp[DLinqObjectModel#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#3)]
 [!code-vb[DLinqObjectModel#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#3)]  
  
 Дополнительные сведения см. в разделе атрибут Association [сопоставление, основанное на атрибутах](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## <a name="linq-to-sql-methods-and-database-stored-procedures"></a>Хранимые процедуры методов и баз данных LINQ to SQL.  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает хранимые процедуры и пользовательские функции. В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], сопоставить эти абстракции, определенные базой данных с клиентскими объектами так, что они будут доступны в режиме строгой типизации из клиентского кода. Подписи методов очень схожи с сигнатурами процедур и функций, определенных в базе данных. Для определения этих методов можно использовать IntelliSense.  
  
 В качестве набора результатов, возвращенного вызовом сопоставленной процедуры, выступает строго типизированная коллекция.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сопоставляет хранимые процедуры и функции с методами с помощью атрибутов <xref:System.Data.Linq.Mapping.FunctionAttribute> и <xref:System.Data.Linq.Mapping.ParameterAttribute>. Методы, представляющие хранимые процедуры, отличаются от методов, представляющих пользовательские функции, свойством <xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A>. Если данное свойство имеет значение `false` (значение по умолчанию), значит метод представляет хранимую процедуру. Если свойству задано значение `true`, метод представляет функцию базы данных.  
  
> [!NOTE]
>  Если вы используете Visual Studio, можно использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для создания методов, сопоставленных с хранимыми процедурами и пользовательскими функциями.  
  
### <a name="example"></a>Пример  
 [!code-csharp[DLinqObjectModel#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#4)]
 [!code-vb[DLinqObjectModel#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#4)]  
  
 Дополнительные сведения см. в разделах атрибут функции, хранимые процедуры атрибут и атрибут параметра [сопоставление, основанное на атрибутах](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md) и [хранимые процедуры](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).  
  
## <a name="see-also"></a>См. также

- [Сопоставление, основанное на атрибутах](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)
- [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
