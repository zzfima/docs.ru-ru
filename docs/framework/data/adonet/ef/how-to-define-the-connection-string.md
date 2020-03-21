---
title: Практическое руководство. Определение строки подключения
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: e5b675a50f883825cce97275048447b79b64cc97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150575"
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="45cc6-102">Практическое руководство. Определение строки подключения</span><span class="sxs-lookup"><span data-stu-id="45cc6-102">How to: Define the Connection String</span></span>

<span data-ttu-id="45cc6-103">В этом разделе показано, как определить строку соединения, используемую при подключении к концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="45cc6-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="45cc6-104">Эта тема основана на концептуальной модели [AdventureWorks Sales.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="45cc6-104">This topic is based on the [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="45cc6-105">Модель AdventureWorks Sales используется во всех разделах документации платформы Entity Framework, описывающих выполнение задач.</span><span class="sxs-lookup"><span data-stu-id="45cc6-105">The AdventureWorks Sales Model is used throughout the task-related topics in the Entity Framework documentation.</span></span> <span data-ttu-id="45cc6-106">Эта тема предполагает, что вы уже настроили рамку сущности и определили модель продаж AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="45cc6-106">This topic assumes that you have already configured the Entity Framework and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="45cc6-107">Для получения дополнительной информации [см. Как: Вручную определить модель и картографические файлы](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="45cc6-107">For more information, see [How to: Manually Define the Model and Mapping Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="45cc6-108">Процедуры в этой теме также включены в [Как: Вручную настроить рамочный проект entity](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="45cc6-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="45cc6-109">Если вы используете Волшебник модели данных Сущности в проекте Visual Studio, он автоматически генерирует файл .edmx и настраивает проект на использование рамочной программы Entity.</span><span class="sxs-lookup"><span data-stu-id="45cc6-109">If you use the Entity Data Model Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the Entity Framework.</span></span> <span data-ttu-id="45cc6-110">Для получения дополнительной информации [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="45cc6-110">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="45cc6-111">Определение строки соединения Entity Framework</span><span class="sxs-lookup"><span data-stu-id="45cc6-111">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="45cc6-112">Откройте файл конфигурации приложения (app.config) и добавьте следующую строку соединения:</span><span class="sxs-lookup"><span data-stu-id="45cc6-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities"
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="45cc6-113">Если в проекте нет файла конфигурации приложения, вы можете добавить его, выбрав **добавить новый элемент** из меню **проекта,** выбрав **общую** категорию, выбрав **файл конфигурации приложения,** а затем нажав **добавить.**</span><span class="sxs-lookup"><span data-stu-id="45cc6-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="45cc6-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="45cc6-114">See also</span></span>

- <span data-ttu-id="45cc6-115">[Краткое руководство](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="45cc6-115">[Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="45cc6-116">[Как создать новый EDMX-файл](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="45cc6-116">[How to: Create a New .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="45cc6-117">[Средства работы с моделью EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="45cc6-117">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
