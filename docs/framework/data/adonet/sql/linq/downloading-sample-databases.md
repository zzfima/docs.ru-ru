---
title: Получение образцов баз данных, примеры кода ADO.NET
description: Загрузите примеры баз данных, используемые в примерах кода в документации по ADO.NET, а также средства SQL Server и управления
ms.date: 10/12/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 75ae1895d683b669f51b33130fc2f47010e39814
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347528"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="04370-103">Получение образцов баз данных, примеры кода ADO.NET</span><span class="sxs-lookup"><span data-stu-id="04370-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="04370-104">Ряд примеров и пошаговых руководствах [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использовать документацию, образцы баз данных и SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="04370-104">A number of samples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample databases and SQL Server Express.</span></span> <span data-ttu-id="04370-105">Можно загрузить эти продукты бесплатно от корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="04370-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-adventureworks-sample-database"></a><span data-ttu-id="04370-106">Получить образец базы данных AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="04370-106">Get the AdventureWorks sample database</span></span>

<span data-ttu-id="04370-107">Загрузите образец базы данных AdventureWorks для следующего репозитория GitHub:</span><span class="sxs-lookup"><span data-stu-id="04370-107">Download the AdventureWorks sample database from the following GitHub repository:</span></span>

[<span data-ttu-id="04370-108">Образцы баз данных AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="04370-108">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="04370-109">После загрузки одной из резервной копии базы данных (\*BAK-файл) файлов, восстановите резервную копию на экземпляре SQL Server с помощью SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="04370-109">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="04370-110">См. в разделе [получить SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="04370-110">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-the-northwind-sample-database"></a><span data-ttu-id="04370-111">Получить образец базы данных "Борей"</span><span class="sxs-lookup"><span data-stu-id="04370-111">Get the Northwind sample database</span></span>

<span data-ttu-id="04370-112">Загрузите образец базы данных "Борей" со следующей страницы в центре загрузки Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="04370-112">Download the Northwind sample database from the following page in the Microsoft Download Center:</span></span>

[<span data-ttu-id="04370-113">Образцы баз данных Pubs и Northwind</span><span class="sxs-lookup"><span data-stu-id="04370-113">Northwind and Pubs Sample Databases</span></span>](https://go.microsoft.com/fwlink?linkid=64296)

<span data-ttu-id="04370-114">После загрузки файла, дважды щелкните файл, чтобы извлечь базы данных и скрипты.</span><span class="sxs-lookup"><span data-stu-id="04370-114">After the file has downloaded, double-click the file to extract the databases and scripts.</span></span> <span data-ttu-id="04370-115">По умолчанию файлы устанавливаются в папке `<drive>:\SQL Server 2000 Sample Databases`.</span><span class="sxs-lookup"><span data-stu-id="04370-115">By default, the files are installed in the folder `<drive>:\SQL Server 2000 Sample Databases`.</span></span>

<span data-ttu-id="04370-116">Перед использованием базы данных Northwind, необходимо выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="04370-116">Before you can use the Northwind database, you have to do one of the following things:</span></span>

- <span data-ttu-id="04370-117">Повторно создать базы данных на экземпляре SQL Server, запустив `instnwnd.sql` файл скрипта в папке установки.</span><span class="sxs-lookup"><span data-stu-id="04370-117">Recreate the database on an instance of SQL Server by running the `instnwnd.sql` script file in the installation folder.</span></span>

- <span data-ttu-id="04370-118">Присоединение `northwnd.mdf` файл с соответствующим ему аргументом `*.ldf` файл журнала на экземпляре SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04370-118">Attach the `northwnd.mdf` file with its corresponding `*.ldf` log file to an instance of SQL Server.</span></span>

## <a name="get_sql"></a> <span data-ttu-id="04370-119">Получить SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="04370-119">Get SQL Server Express</span></span>

<span data-ttu-id="04370-120">SQL Server Express — это бесплатная, начального уровня выпуск SQL Server, можно распространять вместе с приложениями.</span><span class="sxs-lookup"><span data-stu-id="04370-120">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="04370-121">Загрузите SQL Server Express со следующей страницы:</span><span class="sxs-lookup"><span data-stu-id="04370-121">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="04370-122">Выпуски SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="04370-122">SQL Server Express Editions</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="04370-123">Если вы используете [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB включается в Community edition, а также выпуски Professional и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="04370-123">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the Community edition as well as the Professional and higher editions.</span></span>  

## <a name="get_ssms"></a> <span data-ttu-id="04370-124">Получить SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="04370-124">Get SQL Server Management Studio</span></span>
<span data-ttu-id="04370-125">Если вы хотите просмотреть или изменить базу данных, который вы скачали, можно использовать SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="04370-125">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="04370-126">Скачайте SSMS на следующей странице:</span><span class="sxs-lookup"><span data-stu-id="04370-126">Download SSMS from the following page:</span></span>

[<span data-ttu-id="04370-127">Скачать SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="04370-127">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="04370-128">Можно также просматривать и управлять базами данных в среде разработки Visual Studio (IDE).</span><span class="sxs-lookup"><span data-stu-id="04370-128">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="04370-129">В [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), соединиться с базой данных из **обозреватель объектов SQL Server**, или создайте подключение данных к базе данных в **обозревателя серверов**.</span><span class="sxs-lookup"><span data-stu-id="04370-129">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="04370-130">Эти панели обозревателя из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="04370-130">Open these explorer panes from the **View** menu.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="04370-131">См. также</span><span class="sxs-lookup"><span data-stu-id="04370-131">See also</span></span>

- [<span data-ttu-id="04370-132">Начало работы</span><span class="sxs-lookup"><span data-stu-id="04370-132">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
