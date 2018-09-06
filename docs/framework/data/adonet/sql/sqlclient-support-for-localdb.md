---
title: Поддержка SqlClient LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 1ef75def3f3de44b5e23cb1197a4410dcf6b547f
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43886335"
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="4f6b5-102">Поддержка SqlClient LocalDB</span><span class="sxs-lookup"><span data-stu-id="4f6b5-102">SqlClient Support for LocalDB</span></span>
<span data-ttu-id="4f6b5-103">Начиная с SQL Server с рабочим названием Denali, облегченная версия SQL Server, называемая LocalDB, будут доступны.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-103">Beginning in SQL Server code name Denali, a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="4f6b5-104">В этом разделе описывается, как установить подключение к базе данных LocalDB.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-104">This topic discusses how to connect to a LocalDB database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f6b5-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f6b5-105">Remarks</span></span>  
 <span data-ttu-id="4f6b5-106">Дополнительные сведения о LocalDB, включая установку и настройку экземпляра LocalDB см. в разделе электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="4f6b5-107">Обзор возможностей LocalDB:</span><span class="sxs-lookup"><span data-stu-id="4f6b5-107">To summarize what you can do with LocalDB:</span></span>  
  
-   <span data-ttu-id="4f6b5-108">Создание и запуск экземпляров LocalDB через sqllocaldb.exe или файл app.config.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-108">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
-   <span data-ttu-id="4f6b5-109">Использование sqlcmd.exe для добавления и изменения базы данных в экземпляре LocalDB.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-109">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="4f6b5-110">Например, `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-110">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
-   <span data-ttu-id="4f6b5-111">Чтобы добавить базу данных к своему экземпляру LocalDB, пользуйтесь ключевым словом строки подключения `AttachDBFilename` .</span><span class="sxs-lookup"><span data-stu-id="4f6b5-111">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="4f6b5-112">Если при использовании `AttachDBFilename`не указано имя базы данных ключевым словом строки подключения `Database` , то база данных удаляется из экземпляра LocalDB после завершения работы приложения.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-112">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
-   <span data-ttu-id="4f6b5-113">Укажите экземпляр LocalDB в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-113">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="4f6b5-114">Например, если экземпляр имеет имя `myInstance`, то строка подключения включает следующее:</span><span class="sxs-lookup"><span data-stu-id="4f6b5-114">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    ```  
    server=(localdb)\\myInstance  
    ```  
  
 <span data-ttu-id="4f6b5-115">Указание`User Instance=True` недопустимо, если производится соединение с базой данных LocalDB.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-115">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
 <span data-ttu-id="4f6b5-116">Вы можете скачать LocalDB из [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065).</span><span class="sxs-lookup"><span data-stu-id="4f6b5-116">You can download LocalDB from [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065).</span></span> <span data-ttu-id="4f6b5-117">Если вы будете использовать sqlcmd.exe для изменения данных в экземпляре LocalDB, вам потребуется sqlcmd из SQL Server 2012, который также можно получить из пакета дополнительных компонентов SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-117">If you will use sqlcmd.exe to modify data in your LocalDB instance, you will need sqlcmd from SQL Server 2012, which you can also get from the SQL Server 2012 Feature Pack.</span></span>  
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="4f6b5-118">Создание именованного экземпляра программным путем</span><span class="sxs-lookup"><span data-stu-id="4f6b5-118">Programmatically Create a Named Instance</span></span>  
 <span data-ttu-id="4f6b5-119">В приложении можно создать именованный экземпляр и определить базу данных следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-119">An application can create a named instance and specify a database as follows:</span></span>  
  
-   <span data-ttu-id="4f6b5-120">Определите создаваемые экземпляры LocalDB в файле app.config, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-120">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="4f6b5-121">Номер версии экземпляра должен совпадать с номером версии установки LocalDB.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-121">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="4f6b5-122">Укажите имя экземпляра с помощью ключевого слова строки подключения `server` .</span><span class="sxs-lookup"><span data-stu-id="4f6b5-122">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="4f6b5-123">Имя экземпляра, указанное в ключевом слове строки подключения `server` , должно соответствовать имени, указанному в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-123">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
-   <span data-ttu-id="4f6b5-124">С помощью ключевого слова строки подключения `AttachDBFilename` укажите MDF-файл.</span><span class="sxs-lookup"><span data-stu-id="4f6b5-124">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f6b5-125">См. также</span><span class="sxs-lookup"><span data-stu-id="4f6b5-125">See Also</span></span>  
 [<span data-ttu-id="4f6b5-126">Возможности SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4f6b5-126">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [<span data-ttu-id="4f6b5-127">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4f6b5-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
