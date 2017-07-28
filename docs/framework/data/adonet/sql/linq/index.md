---
title: "LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] является компонентом [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] версии 3.5, предоставляющим инфраструктуру времени выполнения для управления реляционными данными как объектами.  
  
> [!NOTE]
>  Реляционные данные отображаются в виде коллекции двумерных таблиц \(*отношений* или *плоских файлов*\),где общие столбцы связывают таблицы друг с другом.  Для эффективного использования [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] необходимо ознакомиться с основными принципами реляционных баз данных.  
  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] модель данных реляционной базы данных сопоставляется объектной модели, выраженной в языке программирования разработчика.  При запуске приложения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует запросы LINQ из объектной модели в SQL и отправляет их в базу данных для выполнения. Когда база данных возвращает результаты, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует их обратно в объекты, с которыми можно работать на собственном языке программирования.  
  
 Пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], как правило, пользуются конструктором [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], который предоставляет пользовательский интерфейс для реализации многих функций [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 Документация, включенная в эту версию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], описывает основные строительные блоки, процессы и методики, необходимые для построения приложений [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  Можно также поискать в библиотеке MSDN конкретные вопросы и принять участие в форуме [LINQ Forum](http://go.microsoft.com/fwlink/?LinkId=76488), где можно подробно обсудить со специалистами более сложные вопросы.  Наконец, в техническом документе [LINQ to SQL: запросы LINQ .NET для реляционных данных](http://go.microsoft.com/fwlink/?LinkId=93205) \(на английском языке\) подробно описывается технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и приводятся примеры кода на языках [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] и C\#.  
  
## В этом подразделе  
 [Начало работы](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 Содержит краткие общие сведения о [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], а также сведения о начале работы с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Руководство по программированию](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 Содержит описание действий по сопоставлению, осуществлению запросов, обновлению, отладке и выполнению схожих задач.  
  
 [Ссылки](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 Содержит справочные сведения о ряде аспектов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  Представлены следующие разделы: "Сопоставление типов SQL\-CLR", "Преобразование стандартного оператора запросов" и многие другие.  
  
 [Образцы](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 Содержит ссылки на примеры [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] и C\#.  
  
## Связанные подразделы  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)  
 Предоставляет общие сведения о технологиях [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  
  
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)  
 Содержит описание технологий [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] для пользователей [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)].  
  
 [LINQ to ADO.NET](http://msdn.microsoft.com/ru-ru/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 Ссылки на портал [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)].  
  
 [Пошаговые руководства LINQ to SQL](http://msdn.microsoft.com/ru-ru/308e66ac-f704-4e00-9b4e-7af0045a2374)  
 Содержит список пошаговых руководств, доступных для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Загрузка образцов баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 Содержит инструкции по загрузке примеров баз данных, используемых в документации.  
  
 [Общие сведения о технологии LinqDataSource](http://msdn.microsoft.com/ru-ru/104cfc3f-7385-47d3-8a51-830dfa791136)  
 Описывает, каким образом элемент управления <xref:System.Web.UI.WebControls.LinqDataSource> предоставляет [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] для веб\-разработчиков посредством архитектуры элементов управления источниками данных [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)].