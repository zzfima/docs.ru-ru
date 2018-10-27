---
title: Получение образцов баз данных, примеры кода ADO.NET
description: Загрузите примеры баз данных, используемые в примерах кода в документации по ADO.NET, а также средства SQL Server и управления
ms.date: 10/18/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 9779300288135cb9332a028d547ce55a07e89471
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188395"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="f57a1-103">Получение образцов баз данных, примеры кода ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f57a1-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="f57a1-104">Ряд примеров и пошаговых руководствах [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использовать документацию, образцы баз данных и SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="f57a1-104">A number of samples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample databases and SQL Server Express.</span></span> <span data-ttu-id="f57a1-105">Можно загрузить эти продукты бесплатно от корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f57a1-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database"></a><span data-ttu-id="f57a1-106">Получить образец базы данных "Борей"</span><span class="sxs-lookup"><span data-stu-id="f57a1-106">Get the Northwind sample database</span></span>

<span data-ttu-id="f57a1-107">Загрузите образец базы данных "Борей" со следующей страницы в центре загрузки Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="f57a1-107">Download the Northwind sample database from the following page in the Microsoft Download Center:</span></span>

[<span data-ttu-id="f57a1-108">Образцы баз данных Pubs и Northwind</span><span class="sxs-lookup"><span data-stu-id="f57a1-108">Northwind and Pubs Sample Databases</span></span>](https://go.microsoft.com/fwlink?linkid=64296)

<span data-ttu-id="f57a1-109">После загрузки файла, дважды щелкните файл, чтобы извлечь базы данных и скрипты.</span><span class="sxs-lookup"><span data-stu-id="f57a1-109">After the file has downloaded, double-click the file to extract the databases and scripts.</span></span> <span data-ttu-id="f57a1-110">По умолчанию файлы устанавливаются в папке `<drive>:\SQL Server 2000 Sample Databases`.</span><span class="sxs-lookup"><span data-stu-id="f57a1-110">By default, the files are installed in the folder `<drive>:\SQL Server 2000 Sample Databases`.</span></span>

<span data-ttu-id="f57a1-111">Прежде чем использовать базы данных Northwind, необходимо воссоздать базу данных на экземпляре SQL Server с помощью [SQL Server Management Studio](#get_ssms) или аналогичное средство для выполнения `instnwnd.sql` файл скрипта в папке установки.</span><span class="sxs-lookup"><span data-stu-id="f57a1-111">Before you can use the Northwind database, you have to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool to run the `instnwnd.sql` script file in the installation folder.</span></span>

## <a name="get-the-adventureworks-sample-database"></a><span data-ttu-id="f57a1-112">Получить образец базы данных AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="f57a1-112">Get the AdventureWorks sample database</span></span>

<span data-ttu-id="f57a1-113">Загрузите образец базы данных AdventureWorks для следующего репозитория GitHub:</span><span class="sxs-lookup"><span data-stu-id="f57a1-113">Download the AdventureWorks sample database from the following GitHub repository:</span></span>

[<span data-ttu-id="f57a1-114">Образцы баз данных AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="f57a1-114">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="f57a1-115">После загрузки одной из резервной копии базы данных (\*BAK-файл) файлов, восстановите резервную копию на экземпляре SQL Server с помощью SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="f57a1-115">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="f57a1-116">См. в разделе [получить SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="f57a1-116">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get_sql"></a> <span data-ttu-id="f57a1-117">Получить SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="f57a1-117">Get SQL Server Express</span></span>

<span data-ttu-id="f57a1-118">SQL Server Express — это бесплатная, начального уровня выпуск SQL Server, можно распространять вместе с приложениями.</span><span class="sxs-lookup"><span data-stu-id="f57a1-118">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="f57a1-119">Загрузите SQL Server Express со следующей страницы:</span><span class="sxs-lookup"><span data-stu-id="f57a1-119">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="f57a1-120">Выпуски SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="f57a1-120">SQL Server Express Editions</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="f57a1-121">Если вы используете [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB включено в бесплатный выпуск Community edition, а также выпуски Professional и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f57a1-121">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition as well as the Professional and higher editions.</span></span>  

## <a name="get_ssms"></a> <span data-ttu-id="f57a1-122">Получить SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f57a1-122">Get SQL Server Management Studio</span></span>
<span data-ttu-id="f57a1-123">Если вы хотите просмотреть или изменить базу данных, который вы скачали, можно использовать SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="f57a1-123">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="f57a1-124">Скачайте SSMS на следующей странице:</span><span class="sxs-lookup"><span data-stu-id="f57a1-124">Download SSMS from the following page:</span></span>

[<span data-ttu-id="f57a1-125">Скачать SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="f57a1-125">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="f57a1-126">Можно также просматривать и управлять базами данных в среде разработки Visual Studio (IDE).</span><span class="sxs-lookup"><span data-stu-id="f57a1-126">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="f57a1-127">В [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), соединиться с базой данных из **обозреватель объектов SQL Server**, или создайте подключение данных к базе данных в **обозревателя серверов**.</span><span class="sxs-lookup"><span data-stu-id="f57a1-127">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="f57a1-128">Эти панели обозревателя из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="f57a1-128">Open these explorer panes from the **View** menu.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f57a1-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f57a1-129">See also</span></span>

- [<span data-ttu-id="f57a1-130">Начало работы</span><span class="sxs-lookup"><span data-stu-id="f57a1-130">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
