---
title: "Работа с языком описания данных DDL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: dc2642df7cfe0f0a4b56537d0b2ebeae34304145
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="working-with-data-definition-language"></a><span data-ttu-id="8d724-102">Работа с языком описания данных DDL</span><span class="sxs-lookup"><span data-stu-id="8d724-102">Working with Data Definition Language</span></span>
<span data-ttu-id="8d724-103">Начиная с [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] версии 4, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] поддерживает язык описания данных (DDL).</span><span class="sxs-lookup"><span data-stu-id="8d724-103">Starting with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] version 4, the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supports data definition language (DDL).</span></span> <span data-ttu-id="8d724-104">Это позволяет создавать и удалять экземпляры базы данных с использованием строки подключения и метаданных модели хранения (SSDL).</span><span class="sxs-lookup"><span data-stu-id="8d724-104">This allows you to create or delete a database instance based on the connection string and the metadata of the storage (SSDL) model.</span></span>  
  
 <span data-ttu-id="8d724-105">В следующих методах в <xref:System.Data.Objects.ObjectContext> с помощью строки соединения и содержимого SSDL выполняются следующие задачи: создание базы данных, удаление базы данных, проверка наличия базы данных и просмотр сформированного скрипта DDL.</span><span class="sxs-lookup"><span data-stu-id="8d724-105">The following methods on the <xref:System.Data.Objects.ObjectContext> use the connection string and the SSDL content to accomplish the following: create or delete the database, check whether the database exists, and view the generated DDL script:</span></span>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  <span data-ttu-id="8d724-106">Предполагается наличие достаточных разрешений для выполнения команд DDL.</span><span class="sxs-lookup"><span data-stu-id="8d724-106">Executing the DDL commands assumes sufficient permissions.</span></span>  
  
 <span data-ttu-id="8d724-107">Ранее указанные методы делегируют большую часть работы базовому поставщику данных ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="8d724-107">The methods previously listed delegate most of the work to the underlying ADO.NET data provider.</span></span> <span data-ttu-id="8d724-108">Поставщик отвечает за соблюдение соглашения об именах, применяемых при создании объектов базы данных, в соответствии с правилами, используемыми для запросов и обновлений.</span><span class="sxs-lookup"><span data-stu-id="8d724-108">It is the provider’s responsibility to ensure that the naming convention used to generate database objects is consistent with conventions used for querying and updates.</span></span>  
  
 <span data-ttu-id="8d724-109">В следующем примере показано, как создать базу данных по существующей модели.</span><span class="sxs-lookup"><span data-stu-id="8d724-109">The following example shows you how to generate the database based on the existing model.</span></span> <span data-ttu-id="8d724-110">Кроме того, новый объект сущности добавляется в контекст объекта, а затем сохраняется в базе данных.</span><span class="sxs-lookup"><span data-stu-id="8d724-110">It also adds a new entity object to the object context and then saves it to the database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="8d724-111">Процедуры</span><span class="sxs-lookup"><span data-stu-id="8d724-111">Procedures</span></span>  
  
#### <a name="to-define-a-database-based-on-the-existing-model"></a><span data-ttu-id="8d724-112">Определение базы данных по существующей модели</span><span class="sxs-lookup"><span data-stu-id="8d724-112">To define a database based on the existing model</span></span>  
  
1.  <span data-ttu-id="8d724-113">Создайте консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="8d724-113">Create a console application.</span></span>  
  
2.  <span data-ttu-id="8d724-114">Добавьте существующую модель в приложение.</span><span class="sxs-lookup"><span data-stu-id="8d724-114">Add an existing model to your application.</span></span>  
  
    1.  <span data-ttu-id="8d724-115">Добавьте пустую модель с именем `SchoolModel`.</span><span class="sxs-lookup"><span data-stu-id="8d724-115">Add an empty model named `SchoolModel`.</span></span> <span data-ttu-id="8d724-116">Чтобы создать пустую модель, см. [как: Создание нового .edmx файл](http://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2) раздела.</span><span class="sxs-lookup"><span data-stu-id="8d724-116">To create an empty model, see the [How to: Create a New .edmx File](http://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2) topic.</span></span>  
  
     <span data-ttu-id="8d724-117">В проект будет добавлен файл SchoolModel.edmx.</span><span class="sxs-lookup"><span data-stu-id="8d724-117">The SchoolModel.edmx file is added to your project.</span></span>  
  
    1.  <span data-ttu-id="8d724-118">Скопируйте концептуальные, хранения и сопоставления содержимого для модели School из [модели School](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) раздела.</span><span class="sxs-lookup"><span data-stu-id="8d724-118">Copy the conceptual, storage, and mapping content for the School model from the [School Model](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) topic.</span></span>  
  
    2.  <span data-ttu-id="8d724-119">Откройте файл SchoolModel.edmx и вставьте нужное содержимое в тегах `edmx:Runtime`.</span><span class="sxs-lookup"><span data-stu-id="8d724-119">Open the SchoolModel.edmx file and paste the content within the `edmx:Runtime` tags.</span></span>  
  
3.  <span data-ttu-id="8d724-120">Добавьте следующий код в функцию main.</span><span class="sxs-lookup"><span data-stu-id="8d724-120">Add the following code to your main function.</span></span> <span data-ttu-id="8d724-121">Этот код инициализирует строку подключения с сервером базы данных, просматривает скрипт DDL, создает базу данных, добавляет новую сущность в контекст и сохраняет изменения в базе данных.</span><span class="sxs-lookup"><span data-stu-id="8d724-121">The code initializes the connection string to your database server, views the DDL script, creates the database, adds a new entity to the context, and saves the changes to the database.</span></span>  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]
