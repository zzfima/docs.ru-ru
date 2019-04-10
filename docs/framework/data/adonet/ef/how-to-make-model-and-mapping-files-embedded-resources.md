---
title: Практическое руководство. Создание встроенных ресурсов файлов модели и сопоставления
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: eae3681664ab1fd095487a7b7ed395302faf2588
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329535"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="442a7-102">Практическое руководство. Создание встроенных ресурсов файлов модели и сопоставления</span><span class="sxs-lookup"><span data-stu-id="442a7-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="442a7-103">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Позволяет развертывать файлы модели и сопоставления как внедренные ресурсы приложения.</span><span class="sxs-lookup"><span data-stu-id="442a7-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="442a7-104">Сборка с внедренными файлами моделей и сопоставления должна быть загружена в том же домене приложения, что и соединение сущности.</span><span class="sxs-lookup"><span data-stu-id="442a7-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="442a7-105">Дополнительные сведения см. в статье [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md) (Строки подключения).</span><span class="sxs-lookup"><span data-stu-id="442a7-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="442a7-106">По умолчанию средства [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] внедряют файлы модели и сопоставления.</span><span class="sxs-lookup"><span data-stu-id="442a7-106">By default, the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] tools embed the model and mapping files.</span></span> <span data-ttu-id="442a7-107">При определении файлов модели и сопоставления вручную следует использовать данную процедуру для обеспечения того, чтобы файлы были развернуты как внедренные ресурсы совместно с приложением [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="442a7-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="442a7-108">Чтобы обеспечить поддержку внедренных ресурсов, необходимо повторить эту процедуру после каждого изменения файлов модели и сопоставления.</span><span class="sxs-lookup"><span data-stu-id="442a7-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="442a7-109">Внедрение файлов модели и сопоставления</span><span class="sxs-lookup"><span data-stu-id="442a7-109">To embed model and mapping files</span></span>  
  
1. <span data-ttu-id="442a7-110">В **обозревателе решений**, выберите файл концептуальной (CSDL).</span><span class="sxs-lookup"><span data-stu-id="442a7-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2. <span data-ttu-id="442a7-111">В **свойства** установите **действие при построении** для **внедренный ресурс**.</span><span class="sxs-lookup"><span data-stu-id="442a7-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3. <span data-ttu-id="442a7-112">Повторите шаги 1 и 2 для файла хранения с расширением SSDL и файла сопоставления с расширением MSL.</span><span class="sxs-lookup"><span data-stu-id="442a7-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4. <span data-ttu-id="442a7-113">В **обозревателе решений**, дважды щелкните файл App.config, а затем измените `Metadata` параметр в `connectionString` атрибут на основе одного из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="442a7-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    -   `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    -   `Metadata=` `res://*/<resourceName>;`  
  
    -   `Metadata=res://*;`  
  
     <span data-ttu-id="442a7-114">Дополнительные сведения см. в статье [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md) (Строки подключения).</span><span class="sxs-lookup"><span data-stu-id="442a7-114">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="442a7-115">Пример</span><span class="sxs-lookup"><span data-stu-id="442a7-115">Example</span></span>  
 <span data-ttu-id="442a7-116">Следующая строка подключения ссылается на внедренные файлы модели и сопоставления для [модели AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="442a7-116">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="442a7-117">Эта строка соединения хранится в файле App.config проекта.</span><span class="sxs-lookup"><span data-stu-id="442a7-117">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="442a7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="442a7-118">See also</span></span>

- [<span data-ttu-id="442a7-119">Моделирование и сопоставление</span><span class="sxs-lookup"><span data-stu-id="442a7-119">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="442a7-120">Практическое руководство. Определение строки соединения</span><span class="sxs-lookup"><span data-stu-id="442a7-120">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)
- [<span data-ttu-id="442a7-121">Практическое руководство. Сборка строки соединения EntityConnection</span><span class="sxs-lookup"><span data-stu-id="442a7-121">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)
- [<span data-ttu-id="442a7-122">Средства работы с моделью EDM ADO.NET</span><span class="sxs-lookup"><span data-stu-id="442a7-122">ADO.NET Entity Data Model Tools</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
