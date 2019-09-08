---
title: Модель объектов LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 81dd0c37-e2a4-4694-83b0-f2e49e693810
ms.openlocfilehash: b73904e2347c501b21b2c5933d0b43c7abafeb7c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792310"
---
# <a name="the-linq-to-sql-object-model"></a>Модель объектов LINQ to SQL
В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]службах объектная модель, выраженная в языке программирования разработчика, сопоставляется с моделью данных реляционной базы данных. После этого операции с данными выполняются в соответствии с объектной моделью.  
  
 В данном сценарии команды базы данных (например, `INSERT`) не выполняются в базе данных. Вместо этого изменение значений и выполнение методов происходит в рамках объектной модели. Если необходимо отправить запрос к базе данных или передать изменения, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует требования в корректные команды SQL и отправляет эти команды в базу данных.  
  
 ![Снимок экрана, на котором показана объектная модель LINQ.](./media/the-linq-to-sql-object-model/linq-object-model-two-tier.png)  
  
 Наиболее фундаментальные элементы в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объектной модели и их связи с элементами в реляционной модели данных приведены в следующей таблице:  
  
|Объектная модель LINQ to SQL|Реляционная модель данных|  
|------------------------------|---------------------------|  
|Класс сущностей|Таблица|  
|Член класса|Столбец|  
|Ассоциация|Отношение внешнего ключа|  
|Метод|Хранимая процедура или функция|  
  
> [!NOTE]
> Следующие сведения подразумевают наличие базовых знаний о реляционной модели данных и правилах.  
  
## <a name="linq-to-sql-entity-classes-and-database-tables"></a>Таблицы классов сущностей и баз данных LINQ to SQL  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]таблица базы данных представлена *классом сущностей*. Класс сущностей аналогичен любому другому создаваемому классу за исключением того, что для снабжения класса примечаниями используются специальные данные, связывающие его с таблицей базы данных. Для этого к объявлению класса добавляется пользовательский атрибут (<xref:System.Data.Linq.Mapping.TableAttribute>), как показано в следующем примере.  
  
### <a name="example"></a>Пример  
 [!code-csharp[DLinqObjectModel#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#1)]
 [!code-vb[DLinqObjectModel#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#1)]  
  
 В базе данных могут быть сохранены только экземпляры классов, объявленные как таблицы (то есть классы сущностей).  
  
 Дополнительные сведения см. в разделе табличный атрибут в [сопоставлении на основе атрибутов](attribute-based-mapping.md).  
  
## <a name="linq-to-sql-class-members-and-database-columns"></a>Столбцы членов класса и базы данных LINQ to SQL  
 Кроме связывания классов с таблицами, можно назначить поля или свойства для представления столбцов базы данных. Для этого [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определяет атрибут <xref:System.Data.Linq.Mapping.ColumnAttribute>, как показано в следующем примере.  
  
### <a name="example"></a>Пример  
 [!code-csharp[DLinqObjectModel#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#2)]
 [!code-vb[DLinqObjectModel#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#2)]  
  
 В базе данных сохраняются или из нее извлекаются только те поля и свойства, которые сопоставлены столбцам. Поля и свойства, не объявленные в качестве столбцов, считаются временными частями логики приложения.  
  
 Атрибут <xref:System.Data.Linq.Mapping.ColumnAttribute> имеет целый ряд свойств, которые можно использовать для настройки членов, представляющих столбцы (например, назначение члена, представляющего столбец первичного ключа). Дополнительные сведения см. в разделе атрибут столбца в [сопоставлении на основе атрибутов](attribute-based-mapping.md).  
  
## <a name="linq-to-sql-associations-and-database-foreign-key-relationships"></a>Связи и отношения внешнего ключа баз данных LINQ to SQL  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]можно представить ассоциации базы данных (например, связи внешнего ключа с первичным ключом), <xref:System.Data.Linq.Mapping.AssociationAttribute> применяя атрибут. В следующем сегменте кода `Order` класс `Customer` содержит свойство с <xref:System.Data.Linq.Mapping.AssociationAttribute> атрибутом. Это свойство и его атрибут предоставляют класс `Order` с отношением для класса `Customer`.  
  
 В следующем примере кода представлено свойство `Customer` из класса `Order`.  
  
### <a name="example"></a>Пример  
 [!code-csharp[DLinqObjectModel#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#3)]
 [!code-vb[DLinqObjectModel#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#3)]  
  
 Дополнительные сведения см. в разделе Атрибут Association в [сопоставлении на основе атрибутов](attribute-based-mapping.md).  
  
## <a name="linq-to-sql-methods-and-database-stored-procedures"></a>Хранимые процедуры методов и баз данных LINQ to SQL.  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает хранимые процедуры и пользовательские функции. В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]эти абстракции, определенные в базе данных, сопоставляются с клиентскими объектами, что позволяет обращаться к ним строго типизированным способом из клиентского кода. Подписи методов очень схожи с сигнатурами процедур и функций, определенных в базе данных. Для определения этих методов можно использовать IntelliSense.  
  
 В качестве набора результатов, возвращенного вызовом сопоставленной процедуры, выступает строго типизированная коллекция.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сопоставляет хранимые процедуры и функции с методами с помощью атрибутов <xref:System.Data.Linq.Mapping.FunctionAttribute> и <xref:System.Data.Linq.Mapping.ParameterAttribute>. Методы, представляющие хранимые процедуры, отличаются от методов, представляющих пользовательские функции, свойством <xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A>. Если данное свойство имеет значение `false` (значение по умолчанию), значит метод представляет хранимую процедуру. Если свойству задано значение `true`, метод представляет функцию базы данных.  
  
> [!NOTE]
> При использовании Visual Studio можно использовать реляционный конструктор объектов для создания методов, сопоставленных с хранимыми процедурами и определяемыми пользователем функциями.  
  
### <a name="example"></a>Пример  
 [!code-csharp[DLinqObjectModel#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#4)]
 [!code-vb[DLinqObjectModel#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#4)]  
  
 Дополнительные сведения см. в разделах атрибут функции, атрибут хранимой процедуры и атрибуты параметра в [сопоставлении на основе атрибутов](attribute-based-mapping.md) и [хранимых процедурах](stored-procedures.md).  
  
## <a name="see-also"></a>См. также

- [Сопоставление, основанное на атрибутах](attribute-based-mapping.md)
- [Основные сведения](background-information.md)
