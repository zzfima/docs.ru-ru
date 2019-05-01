---
title: Практическое руководство. Как сопоставлять связи баз данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
ms.openlocfilehash: 40e376f2c2584490273ec27b78fe5315cbb0315e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033726"
---
# <a name="how-to-map-database-relationships"></a>Практическое руководство. Как сопоставлять связи баз данных
Отношения данных, которые всегда останутся неизменными, можно закодировать в виде ссылок в классе сущностей. В учебной базе данных Northwind, всегда существует связь между заказчиками и их заказами, т.к. обычно заказчики размещают заказы.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Определяет <xref:System.Data.Linq.Mapping.AssociationAttribute> атрибута с помощью которого представляются такие отношения. Этот атрибут используется совместно с типами <xref:System.Data.Linq.EntitySet%601> и <xref:System.Data.Linq.EntityRef%601> для представления в базе данных связи по внешнему ключу. Дополнительные сведения см. в разделе атрибут Association [сопоставление, основанное на атрибутах](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
> [!NOTE]
>  В значениях свойства Storage для атрибутов AssociationAttribute и ColumnAttribute учитывается регистр. Например, следует убедиться в том, что регистр символов в значении, использованном в атрибуте свойства AssociationAttribute.Storage, соответствует регистру символов в соответствующих именах свойств в остальном коде. Это относится ко всем языкам программирования .NET, включая те, которые обычно регистр не учитывается, включая Visual Basic. Дополнительные сведения о свойстве Storage см. в разделе <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
 Большинство связей имеют тип «один ко многим», как и в примере, представленном далее в этом разделе. Отношения "один-к-одному" и "один-ко-многим" можно представить следующим образом.  
  
- Один к одному. Этот тип связей представляется включением элементов <xref:System.Data.Linq.EntitySet%601> с обеих сторон.  
  
     Например, рассмотрим `Customer` - `SecurityCode` связи, созданные таким образом, чтобы код безопасности клиента не будет найден в `Customer` таблицы и может осуществляться только авторизованными лицами.  
  
- Многие ко многим. В связях многие ко многим, первичный ключ связанной таблицы (также называется *соединения* таблицы) часто формируется составлением внешних ключей из двух других таблиц.  
  
     Например, рассмотрим `Employee` - `Project` отношение многие ко многим, сформированное с помощью связанной таблицы `EmployeeProject`. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] требует, чтобы такая связь моделировалась по трем классам: `Employee`, `Project` и `EmployeeProject`. В этом случае изменение отношения между `Employee` и `Project` может потребовать обновления первичного ключа `EmployeeProject`. Однако данная ситуация наилучшим образом моделируется для удаления существующего `EmployeeProject` и создания нового `EmployeeProject`.  
  
    > [!NOTE]
    >  Отношения в реляционных базах данных обычно моделируются в виде значений внешнего ключа, ссылающихся на первичные ключи в других таблицах. Для перемещения между ними следует явно связать две таблицы с помощью реляционной *соединения* операции.  
    >   
    >  Объекты в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], с другой стороны, обращаются друг к другу с помощью ссылок свойств или коллекций ссылок, которые можно перейти с использованием *точка* нотации.  
  
## <a name="example"></a>Пример  
 В следующем примере отношения "один-ко-многим" класс `Customer` имеет свойство, объявляющее отношение между клиентами и их заказами.  Свойство `Orders` имеет тип <xref:System.Data.Linq.EntitySet%601>. Этот тип указывает, что данное отношение относится к виду "один-ко-многим" (один клиент - много заказов). Свойство <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A> используется для описания установки данной связи, а именно: путем указания в связанном классе имени свойства, которое будет сравниваться с существующим. В этом примере `CustomerID` свойство сравнивается, так же, как базы данных *соединения* сравнит значением столбца.  
  
> [!NOTE]
>  Если вы используете Visual Studio, можно использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для создания ассоциации между классами.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## <a name="example"></a>Пример  
 Возможна и обратная ситуация. Для описания ассоциации между клиентами и заказами вместо класса `Customer` можно использовать класс `Order`. Чтобы описать обратную связь с клиентом, класс `Order` использует тип <xref:System.Data.Linq.EntityRef%601>, как показано в следующем примере кода.  
  
> [!NOTE]
>  <xref:System.Data.Linq.EntityRef%601> Поддерживает класс *отложенная загрузка*. Дополнительные сведения *см. в разделе* [отложенное или немедленное Загрузка](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Настройка классов сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
