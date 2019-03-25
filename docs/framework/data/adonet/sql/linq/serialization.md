---
title: Serialization2
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a15ae411-8dc2-4ca3-84d2-01c9d5f1972a
ms.openlocfilehash: 56ebe888b816972f8d72873e4fca9f5204e6c772
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58408929"
---
# <a name="serialization"></a>Сериализация
В этом разделе описывается [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] возможности сериализации. В приведенных ниже подразделах приводятся сведения о добавлении сериализации в процессе создания кода во время разработки, а также о поведении классов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] при сериализации во время выполнения.  
  
 Код сериализации можно добавить во время разработки одним из перечисленных ниже методов.  
  
-   В [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], изменить **режим сериализации** свойства **Unidirectional**.  
  
-   В программе командной строки SQLMetal добавьте **/serialization** параметр. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Обзор  
 Код, сгенерированный [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предоставляет возможности отложенной загрузки по умолчанию. Отложенная загрузка - очень удобное средство среднего уровня для прозрачной загрузки данных по требованию. Однако при сериализации с этим средством возникают проблемы, поскольку сериализатор инициирует отложенную загрузку независимо от намерений пользователя. В действительности, при сериализации объекта также сериализуется его транзитивное замыкание для всех исходящих ссылок с отложенной загрузкой.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Возможность сериализации устраняет эту проблему, главным образом с помощью двух механизмов:  
  
-   Режим <xref:System.Data.Linq.DataContext> для выключения отложенной загрузки (<xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>). Дополнительные сведения см. в разделе <xref:System.Data.Linq.DataContext>.  
  
-   Переключение создания кода на создания атрибутов <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType> и <xref:System.Runtime.Serialization.DataMemberAttribute?displayProperty=nameWithType> в создаваемых классах. Главной темой этого раздела является именно этот аспект, включая поведение классов с отложенной загрузкой при сериализации.  
  
### <a name="definitions"></a>Определения  
  
-   *Сериализатор DataContract*: сериализатор, используемый по умолчанию компонентом Windows Communication Framework (WCF) платформы .NET Framework 3.0 или более поздних версий.  
  
-   *Однонаправленная сериализация*: сериализованная версия класса, который содержит только однонаправленное свойство ассоциации (чтобы избежать зацикливания). По соглашению, для сериализации помечается свойство родительской стороны отношения «первичный ключ - внешний ключ». Другая сторона, участвующая в двунаправленном отношении, не сериализуется.  
  
     Однонаправленная сериализация является единственным типом сериализации, поддерживаемым технологией [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
## <a name="code-example"></a>Пример кода  
 В представленном ниже коде используются традиционные классы `Customer` и `Order` из учебной базы данных « Northwind" и демонстрируется, как добавить к этим классам атрибуты сериализации.  
  
 [!code-csharp[DLinqSerialization#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#1)]
 [!code-vb[DLinqSerialization#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#1)]  
  
 [!code-csharp[DLinqSerialization#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#2)]
 [!code-vb[DLinqSerialization#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#2)]  
  
 [!code-csharp[DLinqSerialization#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#3)]
 [!code-vb[DLinqSerialization#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#3)]  
  
 Для краткости в следующем примере для класса `Order` показано только обратное свойство отношения, соответствующее классу `Customer`. Этот класс не имеет атрибута <xref:System.Runtime.Serialization.DataMemberAttribute>, чтобы избежать зацикливания.  
  
 [!code-csharp[DLinqSerialization#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#4)]
 [!code-vb[DLinqSerialization#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#4)]  
  
 [!code-csharp[DLinqSerialization#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#5)]
 [!code-vb[DLinqSerialization#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#5)]  
  
### <a name="how-to-serialize-the-entities"></a>Сериализация сущностей  
 Сущности в коде, показанном в предыдущих примерах, можно сериализовать следующим образом:  
  
 [!code-csharp[DLinqSerialization#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/Program.cs#6)]
 [!code-vb[DLinqSerialization#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/Module1.vb#6)]  
  
### <a name="self-recursive-relationships"></a>Саморекурсивные отношения  
 Саморекурсивные отношения следуют тому же шаблону. Свойство отношения, соответствующее внешнему ключу, не имеет атрибута <xref:System.Runtime.Serialization.DataMemberAttribute>, в то время как родительское свойство этот атрибут имеет.  
  
 Рассмотрим следующий класс, содержащий две саморекурсивные связи: Employee.Manager/Reports и Employee.Mentor/Mentees.  
  
 [!code-csharp[DLinqSerialization#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSerialization/cs/northwind-ser.cs#7)]
 [!code-vb[DLinqSerialization#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSerialization/vb/northwind-ser.vb#7)]  
  
## <a name="see-also"></a>См. также
- [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [SqlMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
- [Практическое руководство. Обеспечение сериализуемости сущностей](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)
