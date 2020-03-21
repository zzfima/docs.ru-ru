---
title: LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: b0660312f540a69911905edd08541ed70cf39bb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174320"
---
# <a name="linq-to-sql"></a>LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]является компонентом версии 3.5 .NET Framework, которая обеспечивает инфраструктуру времени выполнения для управления реляционными данными как объектами.  
  
> [!NOTE]
> Реляционные данные отображаются в виде коллекции двумерных таблиц (*отношений* или *плоских файлов*),где общие столбцы связывают таблицы друг с другом. Для эффективного использования [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] необходимо ознакомиться с основными принципами реляционных баз данных.  
  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] модель данных реляционной базы данных сопоставляется объектной модели, выраженной в языке программирования разработчика. При запуске приложения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует запросы LINQ из объектной модели в SQL и отправляет их в базу данных для выполнения. Когда база данных возвращает результаты, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует их обратно в объекты, с которыми можно работать на собственном языке программирования.  
  
 Разработчики, использующие Visual Studio, обычно используют Object Relational Designer, который [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]предоставляет пользовательский интерфейс для реализации многих функций .  
  
 Документация, включенная в эту версию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], описывает основные строительные блоки, процессы и методики, необходимые для построения приложений [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Вы также можете искать документы Майкрософт по конкретным вопросам, и вы можете принять участие в [форуме LIN's,](https://social.msdn.microsoft.com/forums/home?forum=linqtosql)где вы можете подробно обсудить более сложные темы с экспертами. Наконец, [LIN-к S'L: .NET Язык-интегрированный запрос для реляционных данных](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) белой бумаги детали технологии, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] в комплекте с Visual Basic и C q код примеры.  
  
## <a name="in-this-section"></a>в этом разделе  
 [Начало работы](getting-started.md)  
 Содержит краткие общие сведения о [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], а также сведения о начале работы с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Руководство по программированию](programming-guide.md)  
 Содержит описание действий по сопоставлению, осуществлению запросов, обновлению, отладке и выполнению схожих задач.  
  
 [Справочник](reference.md)  
 Содержит справочные сведения о ряде аспектов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Представлены следующие разделы: "Сопоставление типов SQL-CLR", "Преобразование стандартного оператора запросов" и многие другие.  
  
 [Образцы](samples.md)  
 Предоставляет ссылки на образцы Visual Basic и C.  
  
## <a name="related-sections"></a>См. также  
 [Языковой интегрированный запрос (LIN) - C #](../../../../../csharp/programming-guide/concepts/linq/index.md)\
 Предоставляет обзоры технологий LIN'а в СЗ.

 [LINQ — Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 Предоставляет обзоры технологий LIN'а в Visual Basic.
  
 [LINQ](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 Описывает технологии LIN'а для пользователей Visual Basic.  
  
 [ЛИНЗ и ADO.NET](../../linq-and-ado-net.md)  
 Ссылки на портал ADO.NET.  
  
 [Пошаговые руководства LINQ to SQL](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))  
 Содержит список пошаговых руководств, доступных для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Загрузка примеров баз данных](downloading-sample-databases.md)  
 Содержит инструкции по загрузке примеров баз данных, используемых в документации.  
  
 [Обзор управления веб-сервером LinqDataSource](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))  
 Описывает, <xref:System.Web.UI.WebControls.LinqDataSource> как элемент управления предоставляет веб-разработчикам языковый интегрированный запрос (LINЗ) через ASP.NET архитектуру управления исходным источником данных.
