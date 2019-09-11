---
title: Практическое руководство. Определение строки соединения
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: a78158c7553c0b479b935e3b94931313df912c2f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854657"
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="11454-102">Практическое руководство. Определение строки соединения</span><span class="sxs-lookup"><span data-stu-id="11454-102">How to: Define the Connection String</span></span>

<span data-ttu-id="11454-103">В этом разделе показано, как определить строку соединения, используемую при подключении к концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="11454-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="11454-104">Этот раздел основан на концептуальной модели [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) .</span><span class="sxs-lookup"><span data-stu-id="11454-104">This topic is based on the [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="11454-105">Модель AdventureWorks Sales используется во всех разделах документации платформы Entity Framework, описывающих выполнение задач.</span><span class="sxs-lookup"><span data-stu-id="11454-105">The AdventureWorks Sales Model is used throughout the task-related topics in the Entity Framework documentation.</span></span> <span data-ttu-id="11454-106">В этом разделе предполагается, что вы уже настроили Entity Framework и определили модель AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="11454-106">This topic assumes that you have already configured the Entity Framework and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="11454-107">Дополнительные сведения см. в разделе [Практическое руководство. Вручную Определите файлы](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))модели и сопоставления.</span><span class="sxs-lookup"><span data-stu-id="11454-107">For more information, see [How to: Manually Define the Model and Mapping Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="11454-108">Процедуры, описанные в этом разделе, также [включены в процедуру: Вручную настройте проект](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="11454-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="11454-109">При использовании мастера EDM в проекте Visual Studio он автоматически создает EDMX-файл и настраивает проект для использования Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="11454-109">If you use the Entity Data Model Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the Entity Framework.</span></span> <span data-ttu-id="11454-110">Дополнительные сведения см. в разделе [Практическое руководство. Использование мастера EDM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="11454-110">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="11454-111">Определение строки соединения Entity Framework</span><span class="sxs-lookup"><span data-stu-id="11454-111">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="11454-112">Откройте файл конфигурации приложения (app.config) и добавьте следующую строку соединения:</span><span class="sxs-lookup"><span data-stu-id="11454-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities" 
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="11454-113">Если в проекте нет файла конфигурации приложения, его можно добавить, выбрав в меню **проект** пункт **Добавить новый элемент** , выбрав категорию **Общие** , выбрав **файл конфигурации приложения**, а затем нажав кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="11454-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="11454-114">См. также</span><span class="sxs-lookup"><span data-stu-id="11454-114">See also</span></span>

- <span data-ttu-id="11454-115">[Краткое руководство](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="11454-115">[Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="11454-116">[Практическое руководство. Создание нового EDMX-файла](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="11454-116">[How to: Create a New .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="11454-117">[Средства работы с моделью EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="11454-117">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
