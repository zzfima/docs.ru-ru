---
title: LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: 86c7e9fae270e75d1ba7e9725ded22ea1961311a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911991"
---
# <a name="linq-to-sql"></a>LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]является компонентом .NET Framework версии 3,5, предоставляющей инфраструктуру времени выполнения для управления реляционными данными как объектами.  
  
> [!NOTE]
> Реляционные данные отображаются в виде коллекции двумерных таблиц (*отношений* или *плоских файлов*),где общие столбцы связывают таблицы друг с другом. Для эффективного использования [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] необходимо ознакомиться с основными принципами реляционных баз данных.  
  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] модель данных реляционной базы данных сопоставляется объектной модели, выраженной в языке программирования разработчика. При запуске приложения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует запросы LINQ из объектной модели в SQL и отправляет их в базу данных для выполнения. Когда база данных возвращает результаты, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует их обратно в объекты, с которыми можно работать на собственном языке программирования.  
  
 Разработчики, использующие Visual Studio, обычно используют реляционный конструктор объектов, который предоставляет пользовательский интерфейс для реализации многих функций [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 Документация, включенная в эту версию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], описывает основные строительные блоки, процессы и методики, необходимые для построения приложений [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Можно также выполнить поиск по Документация Майкрософт для конкретных проблем, и вы можете принять участие в [форуме LINQ](https://go.microsoft.com/fwlink/?LinkId=76488), где вы сможете обсуждать более сложные темы подробно с экспертами. Наконец, [LINQ to SQL: запрос к языку .NET для реляционных данных](https://go.microsoft.com/fwlink/?LinkId=93205) , содержащий технические сведения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] о технологии, завершенный с C# Visual Basic и примерами кода.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Начало работы](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 Содержит краткие общие сведения о [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], а также сведения о начале работы с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Руководство по программированию](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 Содержит описание действий по сопоставлению, осуществлению запросов, обновлению, отладке и выполнению схожих задач.  
  
 [Ссылки](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 Содержит справочные сведения о ряде аспектов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Представлены следующие разделы: "Сопоставление типов SQL-CLR", "Преобразование стандартного оператора запросов" и многие другие.  
  
 [Примеры](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 Содержит ссылки на Visual Basic и C# примеры.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Интегрированный в язык запрос (LINQ) —C#](../../../../../csharp/programming-guide/concepts/linq/index.md)\
 Предоставляет обзоры технологий LINQ в C#.
 
 [LINQ — Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 Предоставляет обзоры технологий LINQ в Visual Basic.
  
 [LINQ](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 Описание [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] технологий для Visual Basic пользователей.  
  
 [LINQ и ADO.NET](../../../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 Ссылки на портал ADO.NET.  
  
 [Пошаговые руководства LINQ to SQL](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))  
 Содержит список пошаговых руководств, доступных для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 Содержит инструкции по загрузке примеров баз данных, используемых в документации.  
  
 [Обзор серверного веб-элемента управления LinqDataSource](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))  
 Описывает, как <xref:System.Web.UI.WebControls.LinqDataSource> элемент управления [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] предоставляет веб-разработчикам через архитектуру управления источниками данных ASP.NET.
