---
title: Получение образцов баз данных SQL Server, примеры кода ADO.NET
description: Загрузите примеры баз данных SQL Server, используемые в примерах кода в документации по ADO.NET, а также средства SQL Server и управления
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 5580f06f3d28ed6d70f75b619498ac8de7bc3326
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62037939"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="896aa-103">Получение образцов баз данных, примеры кода ADO.NET</span><span class="sxs-lookup"><span data-stu-id="896aa-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="896aa-104">Ряд примеров и пошаговых руководствах [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использовать документацию, образцы баз данных SQL Server и SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="896aa-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="896aa-105">Можно загрузить эти продукты бесплатно от корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="896aa-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="896aa-106">Получение образца базы данных Northwind для SQL Server</span><span class="sxs-lookup"><span data-stu-id="896aa-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="896aa-107">Скачайте сценарий `instnwnd.sql` из следующий репозиторий GitHub для создания и загрузки образца базы данных Northwind для SQL Server:</span><span class="sxs-lookup"><span data-stu-id="896aa-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="896aa-108">Northwind и pubs образцы баз данных для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="896aa-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="896aa-109">Перед использованием базы данных Northwind, необходимо запустить Скачанный `instnwnd.sql` файла скрипта для воссоздания базы данных на экземпляре SQL Server с помощью [SQL Server Management Studio](#get_ssms) или аналогичное средство.</span><span class="sxs-lookup"><span data-stu-id="896aa-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="896aa-110">Следуйте инструкциям в файле Readme в репозитории.</span><span class="sxs-lookup"><span data-stu-id="896aa-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="896aa-111">Если вам нужны для базы данных "Борей" для Microsoft Access, см. в разделе [установить образец базы данных "Борей" для Microsoft Access](#northwind_access).</span><span class="sxs-lookup"><span data-stu-id="896aa-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="northwind_access"></a> <span data-ttu-id="896aa-112">Получить образец базы данных "Борей" для Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="896aa-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="896aa-113">Образец базы данных "Борей" для Microsoft Access не доступны в центре загрузки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="896aa-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="896aa-114">Чтобы установить Northwind непосредственно из приложения Access, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="896aa-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="896aa-115">Откройте доступ.</span><span class="sxs-lookup"><span data-stu-id="896aa-115">Open Access.</span></span>

1. <span data-ttu-id="896aa-116">Ввод **Northwind** в **поиск шаблонов в Интернете** поле, а затем выберите **ввод**.</span><span class="sxs-lookup"><span data-stu-id="896aa-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="896aa-117">На странице результатов выберите **Northwind**.</span><span class="sxs-lookup"><span data-stu-id="896aa-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="896aa-118">Откроется новое окно с описанием базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="896aa-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="896aa-119">В новом окне в **имя файла** текстовое поле, укажите имя файла для копии базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="896aa-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="896aa-120">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="896aa-120">Select **Create**.</span></span> <span data-ttu-id="896aa-121">Доступ загрузки базы данных Northwind и готовит файл.</span><span class="sxs-lookup"><span data-stu-id="896aa-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="896aa-122">По завершении этого процесса база данных открывается экран с.</span><span class="sxs-lookup"><span data-stu-id="896aa-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="896aa-123">Получить образец базы данных AdventureWorks для SQL Server</span><span class="sxs-lookup"><span data-stu-id="896aa-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="896aa-124">Загрузите образец базы данных AdventureWorks для SQL Server из следующего репозитория GitHub:</span><span class="sxs-lookup"><span data-stu-id="896aa-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="896aa-125">Образцы баз данных AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="896aa-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="896aa-126">После загрузки одной из резервной копии базы данных (\*BAK-файл) файлов, восстановите резервную копию на экземпляре SQL Server с помощью SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="896aa-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="896aa-127">См. в разделе [получить SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="896aa-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get_ssms"></a> <span data-ttu-id="896aa-128">Получить SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="896aa-128">Get SQL Server Management Studio</span></span>
<span data-ttu-id="896aa-129">Если вы хотите просмотреть или изменить базу данных, который вы скачали, можно использовать SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="896aa-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="896aa-130">Скачайте SSMS на следующей странице:</span><span class="sxs-lookup"><span data-stu-id="896aa-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="896aa-131">Скачать SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="896aa-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="896aa-132">Можно также просматривать и управлять базами данных в среде разработки Visual Studio (IDE).</span><span class="sxs-lookup"><span data-stu-id="896aa-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="896aa-133">В [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), соединиться с базой данных из **обозреватель объектов SQL Server**, или создайте подключение данных к базе данных в **обозревателя серверов**.</span><span class="sxs-lookup"><span data-stu-id="896aa-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="896aa-134">Эти панели обозревателя из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="896aa-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get_sql"></a> <span data-ttu-id="896aa-135">Получить SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="896aa-135">Get SQL Server Express</span></span>

<span data-ttu-id="896aa-136">SQL Server Express — это бесплатная, начального уровня выпуск SQL Server, можно распространять вместе с приложениями.</span><span class="sxs-lookup"><span data-stu-id="896aa-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="896aa-137">Загрузите SQL Server Express со следующей страницы:</span><span class="sxs-lookup"><span data-stu-id="896aa-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="896aa-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="896aa-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="896aa-139">Если вы используете [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB включено в бесплатный выпуск Community для Visual Studio, а также выпуски Professional и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="896aa-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="896aa-140">См. также</span><span class="sxs-lookup"><span data-stu-id="896aa-140">See also</span></span>

- [<span data-ttu-id="896aa-141">Начало работы</span><span class="sxs-lookup"><span data-stu-id="896aa-141">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
