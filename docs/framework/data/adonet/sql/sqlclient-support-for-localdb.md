---
title: "Поддержка SqlClient LocalDB"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
caps.latest.revision: "14"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: abe9487f9c2ebbb93c2e712959237f722ee707b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="f7dce-102">Поддержка SqlClient LocalDB</span><span class="sxs-lookup"><span data-stu-id="f7dce-102">SqlClient Support for LocalDB</span></span>
<span data-ttu-id="f7dce-103">Начиная с версии [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] с кодовым наименованием Denali, будет доступна упрощенная версия [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], именуемая LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f7dce-103">Beginning in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] code name Denali, a lightweight version of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], called LocalDB, will be available.</span></span> <span data-ttu-id="f7dce-104">В этом разделе описывается, как установить подключение к базе данных LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f7dce-104">This topic discusses how to connect to a LocalDB database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7dce-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7dce-105">Remarks</span></span>  
 <span data-ttu-id="f7dce-106">Дополнительные сведения о LocalDB, включая установку и настройку экземпляра LocalDB, см. в электронной документации по [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f7dce-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="f7dce-107">Обзор возможностей LocalDB:</span><span class="sxs-lookup"><span data-stu-id="f7dce-107">To summarize what you can do with LocalDB:</span></span>  
  
-   <span data-ttu-id="f7dce-108">Создание и запуск экземпляров LocalDB через sqllocaldb.exe или файл app.config.</span><span class="sxs-lookup"><span data-stu-id="f7dce-108">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
-   <span data-ttu-id="f7dce-109">Использование sqlcmd.exe для добавления и изменения базы данных в экземпляре LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f7dce-109">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="f7dce-110">Например, `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="f7dce-110">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
-   <span data-ttu-id="f7dce-111">Чтобы добавить базу данных к своему экземпляру LocalDB, пользуйтесь ключевым словом строки подключения `AttachDBFilename` .</span><span class="sxs-lookup"><span data-stu-id="f7dce-111">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="f7dce-112">Если при использовании `AttachDBFilename`не указано имя базы данных ключевым словом строки подключения `Database` , то база данных удаляется из экземпляра LocalDB после завершения работы приложения.</span><span class="sxs-lookup"><span data-stu-id="f7dce-112">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
-   <span data-ttu-id="f7dce-113">Укажите экземпляр LocalDB в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="f7dce-113">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="f7dce-114">Например, если экземпляр имеет имя `myInstance`, то строка подключения включает следующее:</span><span class="sxs-lookup"><span data-stu-id="f7dce-114">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    ```  
    server=(localdb)\\myInstance  
    ```  
  
 <span data-ttu-id="f7dce-115">Указание`User Instance=True` недопустимо, если производится соединение с базой данных LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f7dce-115">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
 <span data-ttu-id="f7dce-116">Базу данных LocalDB можно скачать из [пакета дополнительных компонентов Microsoft SQL Server 2012](http://www.microsoft.com/download/en/details.aspx?id=29065).</span><span class="sxs-lookup"><span data-stu-id="f7dce-116">You can download LocalDB from [Microsoft SQL Server 2012 Feature Pack](http://www.microsoft.com/download/en/details.aspx?id=29065).</span></span> <span data-ttu-id="f7dce-117">Если необходимо изменение данных в экземпляре LocalDB с помощью программы sqlcmd.exe, то необходимо пользоваться версией sqlcmd из [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012. Эту программу можно также получить из пакета дополнительных компонентов [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012.</span><span class="sxs-lookup"><span data-stu-id="f7dce-117">If you will use sqlcmd.exe to modify data in your LocalDB instance, you will need sqlcmd from [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012, which you can also get from the [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 Feature Pack.</span></span>  
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="f7dce-118">Создание именованного экземпляра программным путем</span><span class="sxs-lookup"><span data-stu-id="f7dce-118">Programmatically Create a Named Instance</span></span>  
 <span data-ttu-id="f7dce-119">В приложении можно создать именованный экземпляр и определить базу данных следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f7dce-119">An application can create a named instance and specify a database as follows:</span></span>  
  
-   <span data-ttu-id="f7dce-120">Определите создаваемые экземпляры LocalDB в файле app.config, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="f7dce-120">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="f7dce-121">Номер версии экземпляра должен совпадать с номером версии установки LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f7dce-121">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
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
  
-   <span data-ttu-id="f7dce-122">Укажите имя экземпляра с помощью ключевого слова строки подключения `server` .</span><span class="sxs-lookup"><span data-stu-id="f7dce-122">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="f7dce-123">Имя экземпляра, указанное в ключевом слове строки подключения `server` , должно соответствовать имени, указанному в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="f7dce-123">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
-   <span data-ttu-id="f7dce-124">С помощью ключевого слова строки подключения `AttachDBFilename` укажите MDF-файл.</span><span class="sxs-lookup"><span data-stu-id="f7dce-124">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7dce-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f7dce-125">See Also</span></span>  
 [<span data-ttu-id="f7dce-126">Возможности SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f7dce-126">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [<span data-ttu-id="f7dce-127">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f7dce-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
