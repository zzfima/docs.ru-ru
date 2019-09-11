---
title: Практическое руководство. Выполнение запроса, возвращающего сложные типы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: b08b220e969ad1c400413978c85b2f107d64a688
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854641"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a><span data-ttu-id="87e9c-102">Практическое руководство. Выполнение запроса, возвращающего сложные типы</span><span class="sxs-lookup"><span data-stu-id="87e9c-102">How to: Execute a Query that Returns Complex Types</span></span>
<span data-ttu-id="87e9c-103">В этом разделе показано выполнение запроса на языке [!INCLUDE[esql](../../../../../includes/esql-md.md)], который возвращает объекты типа сущности, содержащие свойство сложного типа.</span><span class="sxs-lookup"><span data-stu-id="87e9c-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that returns entity type objects that contain a property of a complex type.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="87e9c-104">Выполнение кода в этом примере</span><span class="sxs-lookup"><span data-stu-id="87e9c-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="87e9c-105">Добавьте [модель AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) в проект и настройте проект для использования Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="87e9c-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="87e9c-106">Дополнительные сведения см. в разделе [Практическое руководство. Используйте мастер](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))EDM.</span><span class="sxs-lookup"><span data-stu-id="87e9c-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="87e9c-107">На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="87e9c-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. <span data-ttu-id="87e9c-108">Дважды щелкните EDMX файл, чтобы отобразить модель в [окне обозревателя моделей](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) Entity Designer.</span><span class="sxs-lookup"><span data-stu-id="87e9c-108">Double click the .edmx file to display the model in the [Model Browser window](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) of the Entity Designer.</span></span> <span data-ttu-id="87e9c-109">На поверхности Entity Designer выберите `Email` свойства `Contact` и `Phone` типа сущности, щелкните правой кнопкой мыши и выберите Рефакторинг для **нового сложного типа**.</span><span class="sxs-lookup"><span data-stu-id="87e9c-109">On the Entity Designer surface, select the `Email` and `Phone` properties of the `Contact` entity type, then right-click and select **Refactor into New Complex Type**.</span></span>  
  
4. <span data-ttu-id="87e9c-110">В **Обозреватель моделей**добавляется новый сложный `Email` тип `Phone` с выбранными свойствами и.</span><span class="sxs-lookup"><span data-stu-id="87e9c-110">A new complex type with the selected `Email` and `Phone` properties is added to the **Model Browser**.</span></span> <span data-ttu-id="87e9c-111">Сложному типу присваивается имя по умолчанию: Переименуйте тип `EmailPhone` в в окне " **Свойства** ".</span><span class="sxs-lookup"><span data-stu-id="87e9c-111">The complex type is given a default name: rename the type to `EmailPhone` in the **Properties** window.</span></span> <span data-ttu-id="87e9c-112">Кроме того, новое свойство `ComplexProperty` добавляется к типу сущности `Contact`.</span><span class="sxs-lookup"><span data-stu-id="87e9c-112">Also, a new `ComplexProperty` property is added to the `Contact` entity type.</span></span> <span data-ttu-id="87e9c-113">Измените имя свойства на `EmailPhoneComplexType.`</span><span class="sxs-lookup"><span data-stu-id="87e9c-113">Rename the property to `EmailPhoneComplexType.`</span></span>  
  
     <span data-ttu-id="87e9c-114">Сведения о создании и изменении сложных типов с помощью мастера EDM см. в разделе [как Рефакторинг существующих свойств в свойство](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) сложного типа и [выполнение следующих действий: Создание и изменение сложных типов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="87e9c-114">For information about creating and modifying complex types by using the Entity Data Model Wizard, see [How to: Refactor Existing Properties into a Complex Type Property](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) and [How to: Create and Modify Complex Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="87e9c-115">Пример</span><span class="sxs-lookup"><span data-stu-id="87e9c-115">Example</span></span>  
 <span data-ttu-id="87e9c-116">В следующем примере выполняется запрос, `Contact` который возвращает коллекцию объектов и отображает два свойства `Contact` объектов: `ContactID` и значения `EmailPhoneComplexType` сложного типа.</span><span class="sxs-lookup"><span data-stu-id="87e9c-116">The following example executes a query that returns a collection of `Contact` objects and displays two properties of the `Contact` objects: `ContactID` and the values of the `EmailPhoneComplexType` complex type.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
