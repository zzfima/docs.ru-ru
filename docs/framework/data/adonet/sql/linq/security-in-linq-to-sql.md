---
title: "Безопасность в LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d49787f7-414e-4c71-aa33-80a5895536b1
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0ee361c27bd14f0266b2b86f315f9c091e049c12
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="security-in-linq-to-sql"></a><span data-ttu-id="eed07-102">Безопасность в LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="eed07-102">Security in LINQ to SQL</span></span>
<span data-ttu-id="eed07-103">При соединении с базой данных всегда присутствуют риски безопасности.</span><span class="sxs-lookup"><span data-stu-id="eed07-103">Security risks are always present when you connect to a database.</span></span> <span data-ttu-id="eed07-104">Хотя в LINQ to SQL включены некоторые новые способы работы с данными в SQL Server, он не предоставляет никаких дополнительных механизмов безопасности.</span><span class="sxs-lookup"><span data-stu-id="eed07-104">Although LINQ to SQL may include some new ways to work with data in SQL Server, it does not provide any additional security mechanisms.</span></span>  
  
## <a name="access-control-and-authentication"></a><span data-ttu-id="eed07-105">Управление доступом и проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="eed07-105">Access Control and Authentication</span></span>  
 <span data-ttu-id="eed07-106">У LINQ to SQL нет своей модели пользователей или механизмов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="eed07-106">LINQ to SQL does not have its own user model or authentication mechanisms.</span></span> <span data-ttu-id="eed07-107">Применяйте SQL Server Security для управления доступом к сопоставленным с вашей моделью объектов базе данных, ее таблицам и представлениям, а также хранимым процедурам.</span><span class="sxs-lookup"><span data-stu-id="eed07-107">Use SQL Server Security to control access to the database, database tables, views, and stored procedures that are mapped to your object model.</span></span> <span data-ttu-id="eed07-108">Предоставляйте пользователям минимальный требуемый доступ и настаивайте на использовании для проверки подлинности надежных паролей.</span><span class="sxs-lookup"><span data-stu-id="eed07-108">Grant the minimally required access to users and require strong passwords for user authentication.</span></span>  
  
## <a name="mapping-and-schema-information"></a><span data-ttu-id="eed07-109">Сопоставление и сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="eed07-109">Mapping and Schema Information</span></span>  
 <span data-ttu-id="eed07-110">Сопоставление типа SQL-CLR и сведения о схеме базы данных в модели объектов, а также внешний файл сопоставления доступны всем, у кого есть доступ к этим файлам в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="eed07-110">SQL-CLR type mapping and database schema information in your object model or external mapping file is available for all with access to those files in the file system.</span></span> <span data-ttu-id="eed07-111">Предполагается, что информация о схеме будет доступна всем, кто может получить доступ к модели объектов или внешнему файлу сопоставления. Для предотвращения распространения доступа к сведениям о схеме пользуйтесь механизмами безопасности файлов, чтобы защитить исходные файлы и файлы сопоставления.</span><span class="sxs-lookup"><span data-stu-id="eed07-111">Assume that schema information will be available to all who can access the object model or external mapping file.To prevent more widespread access to schema information, use file security mechanisms to secure source files and mapping files.</span></span>  
  
## <a name="connection-strings"></a><span data-ttu-id="eed07-112">Строки подключения</span><span class="sxs-lookup"><span data-stu-id="eed07-112">Connection Strings</span></span>  
 <span data-ttu-id="eed07-113">При любой возможности стремитесь избегать использования паролей в строках соединения.</span><span class="sxs-lookup"><span data-stu-id="eed07-113">Using passwords in connection strings should be avoided whenever possible.</span></span> <span data-ttu-id="eed07-114">Строка соединения не только сама по себе представляет риск, но при использовании объектно-реляционного конструктора и средства командной строки SQLMetal она может попасть в раскрытом виде в модель объектов или внешний файл сопоставления.</span><span class="sxs-lookup"><span data-stu-id="eed07-114">Not only is a connection string a security risk in its own right, but the connection string may also be added in clear text to the object model or external mapping file when using the Object Relational Designer or SQLMetal command-line tool.</span></span> <span data-ttu-id="eed07-115">Любой обладатель доступа к модели объектов или внешнему файлу сопоставления через файловую систему сможет увидеть пароль соединения, если он будет включен в строку соединения.</span><span class="sxs-lookup"><span data-stu-id="eed07-115">Anyone with access to the object model or external mapping file via the file system could see the connection password (if it is included in the connection string).</span></span>  
  
 <span data-ttu-id="eed07-116">Для минимизации подобных рисков применяйте встроенную безопасность для установления доверительного соединения с [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eed07-116">To minimize such risks, use integrated security to make a trusted connection with [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="eed07-117">При таком подходе не требуется хранить пароль в строке соединения.</span><span class="sxs-lookup"><span data-stu-id="eed07-117">By using this approach, you do not have to store a password in the connection string.</span></span> <span data-ttu-id="eed07-118">Дополнительные сведения см. в разделе [безопасности SQL Server](../../../../../../docs/framework/data/adonet/sql/sql-server-security.md).</span><span class="sxs-lookup"><span data-stu-id="eed07-118">For more information, see [SQL Server Security](../../../../../../docs/framework/data/adonet/sql/sql-server-security.md).</span></span>  
  
 <span data-ttu-id="eed07-119">При отсутствии встроенной безопасности в строке соединения потребуется открытый текст пароля.</span><span class="sxs-lookup"><span data-stu-id="eed07-119">In the absence of integrated security, a clear-text password will be needed in the connection string.</span></span> <span data-ttu-id="eed07-120">Ниже приведены лучшие способы обеспечения безопасности строки соединения в порядке возрастания риска.</span><span class="sxs-lookup"><span data-stu-id="eed07-120">The best way to help secure your connection string, in increasing order of risk, is as follows:</span></span>  
  
-   <span data-ttu-id="eed07-121">Используйте встроенную безопасность.</span><span class="sxs-lookup"><span data-stu-id="eed07-121">Use integrated security.</span></span>  
  
-   <span data-ttu-id="eed07-122">Обезопасить строки соединения с помощью паролей и минимизировать пересылку строк соединения.</span><span class="sxs-lookup"><span data-stu-id="eed07-122">Secure connection strings with passwords and minimize passing around connection strings.</span></span>  
  
-   <span data-ttu-id="eed07-123">Применяйте класс <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> вместо строки соединения, поскольку он ограничивает длительность просмотра.</span><span class="sxs-lookup"><span data-stu-id="eed07-123">Use a <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> class instead of a connection string since it limits the duration of exposure.</span></span> <span data-ttu-id="eed07-124">В LINQ to SQL создать экземпляр класса <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> можно с помощью атрибута <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="eed07-124">The LINQ to SQL <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> class can be instantiated using a <xref:System.Data.SqlClient.SqlConnection>.</span></span>  
  
-   <span data-ttu-id="eed07-125">Минимизировать время существования и точек соприкосновения для всех строк соединения.</span><span class="sxs-lookup"><span data-stu-id="eed07-125">Minimize lifetimes and touch points for all connection strings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eed07-126">См. также</span><span class="sxs-lookup"><span data-stu-id="eed07-126">See Also</span></span>  
 [<span data-ttu-id="eed07-127">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="eed07-127">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="eed07-128">Часто задаваемые вопросы</span><span class="sxs-lookup"><span data-stu-id="eed07-128">Frequently Asked Questions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)
