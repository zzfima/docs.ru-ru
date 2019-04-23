---
title: Практическое руководство. Как динамически создать базу данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb7f23c4-4572-4c38-9898-a287807d070c
ms.openlocfilehash: ab5e2867ce85fcc82e1114696c129aae878bbee6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072393"
---
# <a name="how-to-dynamically-create-a-database"></a>Практическое руководство. Как динамически создать базу данных
В LINQ to SQL модель объектов сопоставляется с реляционной базой данных. Сопоставление обеспечивается применением для описания структуры реляционной базы данных сопоставления на основе атрибутов или внешнего файла сопоставления. В обоих случаях имеется достаточно сведений о реляционной базе данных, позволяющих создать новый экземпляр базы данных с помощью метода <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>.  
  
 Метод <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> создает реплику базы данных с той степенью подробности, которую позволяет обеспечить информация, закодированная в модели объектов. Файлы сопоставления и атрибуты из модели объектов могут включать не все сведения относительно структуры существующей базы. Сведения сопоставления не представляют содержимого определяемых пользователем функций, хранимых процедур, триггеров и проверочных ограничений. Для большинства баз данных такого поведения достаточно.  
  
 Методом <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> можно воспользоваться в произвольном числе случаев, особенно если доступен известный поставщик данных наподобие Microsoft SQL Server 2008. К числу типовых сценариев относятся.  
  
-   Построение приложения, которое автоматически устанавливает себя на клиентской системе.  
  
-   Построение клиентского приложения, которому требуется локальная база данных для сохранения своего автономного состояния.  
  
 Можно также вызвать с SQL Server метод <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>, указав имя MDF-файла или каталога, в зависимости от строки соединения. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использует строку соединения исходя из создаваемой базы данных и сервера, на котором она должна быть создана.  
  
> [!NOTE]
>  При любой возможности применяйте встроенную безопасность Windows для соединения с базой данных, чтобы не требовались пароли в строке соединения.  
  
## <a name="example"></a>Пример  
 В приведенном ниже коде дан пример того, как создать новую базу данных с именем MyDVDs.mdf.  
  
 [!code-csharp[DLinqSubmittingChanges#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#5)]
 [!code-vb[DLinqSubmittingChanges#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#5)]  
  
## <a name="example"></a>Пример  
 Для создания базы данных можно использовать модель объектов, выполняя следующее:  
  
 [!code-csharp[DLinqSubmittingChanges#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#6)]
 [!code-vb[DLinqSubmittingChanges#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#6)]  
  
## <a name="example"></a>Пример  
 При построении приложения, которое автоматически устанавливает себя на клиентской системе, проверьте, существует ли уже база данных, и удалите ее перед созданием новой базы. Класс <xref:System.Data.Linq.DataContext> предоставляет методы <xref:System.Data.Linq.DataContext.DatabaseExists%2A> и <xref:System.Data.Linq.DataContext.DeleteDatabase%2A> для помощи в этом процессе.  
  
 Следующий пример показывает один из способов применения этих методов для реализации такого подхода.  
  
 [!code-csharp[DLinqSubmittingChanges#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#7)]
 [!code-vb[DLinqSubmittingChanges#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#7)]  
  
## <a name="see-also"></a>См. также

- [Сопоставление, основанное на атрибутах](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)
- [Внешнее сопоставление](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)
- [Сопоставление типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
- [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Внесение и отправка изменений данных](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
